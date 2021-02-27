# Buenas prácticas en Angular

En este documento vamos a exponer una serie de pautas para la realización de un buen código.

## Rendimiento de las vistas

* Realizar un uso responsable de **ngFor**:

  La directiva `ngFor` viene muy bien en las vistas puesto que nos permite repetir trozos de nuestro vista, pero ha de ser mediante un uso responsable puesto que consume muchos recursos. El problema es que tiene esta directiva es que si realizamos una modificación sobre el objeto iterable sobre el que se está haciendo el bucle, hay que rehacer esa parte completa del DOM, lo que hace que el rendimiento de nuestra aplicación caiga, ya que el navegador tiene que volver a renderizar esa parte de la web.
  
  Si sabemos que durante el tiempo de ejecución el contenido del iterable del ngFor va a cambiar, **es muy recomendable el uso de la función** `trackBy`. Mejoramos el rendimiento, puesto que con esta función lo que conseguimos es indicarle al navegador qué parte del DOM se va ver afectada y no tendrá que renderizar todo el bloque del ngFor, sino la parte que se va a ver afectada.
  
  Código en la vista _my-component.component.html_:

  ```html
  <ul>
    <li *ngFor="let item of itemsArray; trackBy: trackByFunction">{{ item }}</li>
  </ul>
  ```

  Definición de la función en el fichero _my-component.component.ts_:

  ```typescript
  public itemsArray: number[] = [1, 2, 3, 4, 5, 6, 7];
  
  ngOnInit(): void {
    //  Metemos un ítem cada segundo.
    setInterval(
      () => itemsArray.push(itemsArray.length + 1),
      1000
    )
  }
  
  public trackByFunction(index: number, item): number {
    if (!item) {
      return null;
    }
    return index;
  }
  ```

  Otro ejemplo:

  ```html
  <ul>
    <li *ngFor="item of itemsArray; trackBy: trackByFn" [id]="item.id"><{{ item.name }} - {{ item.amount }}/li>
  </ul>
  ```

  ```typescript
  interface Product {
    id: number;
    name: string;
    amount: number;
  }
  
  public itemsArray: Product[] = [
    {
      id: 1,
      name: 'Banana',
      amount: 10
    }
  ]
  
  constructor (private productService: ProductService) { }
  
  ngOnInit(): void {
    setInterval(
      () => {
        this.productService.getNewProduct()
          .pipe(takeUntil(this._unsubscribe$)
          .subscribe((newProduct: Product) => {
            this.itemsArray.push(newProduct)
          });
      },
      1000
    )
  }
  
  /**
   * Función para el trackBy del ngFor, buscará por el id del Product.
   */
  public trackByFn(index: number, item: Product): number {
    if (!item) return null;
    return item.id;
  }
  ```

  **Referencias**:
  1. [Documentanción oficial de Angular sobre ngFor](https://angular.io/api/common/NgForOf#ngForTrackBy).
  2. [Improving Angular \*ngFor Performance Throght trackBy](https://medium.com/better-programming/improving-angular-ngfor-performance-through-trackby-ae4cf943b878).
  3. [Angular 7/8 | NgFor and TrackBy quick tutorial by example](https://www.freakyjolly.com/angular-7-8-ngfor-and-trackby-quick-tutorial-by-example/).

* No usar **funciones** en la vista:

  El uso de funciones en la vista hace que se tenga que se active la detección de cambios, eso obliga a realizar un nuevo pintado del DOM, y eso quiere decir que el rendimiento de la aplicación disminuye ya que esta parte es la que más consume en el navegador.
  
  Para qué se utilizan las funciones:
  
  1. Transformación de alguna variable: si este es el caso por el que estamos utilizando una función, la solución es bien sencilla, utiliza una `pipe` de Angular, que hará que solo se cambie el valor de la propiedad pública que estamos mostrando.
  2. Utilización de un _getter_ para una propiedad. Los _getter_ y los _setter_ en sí son funciones, con lo que su utilización en la vista implican que se vaya a realizar un renderizado del DOM en caso de usarlos. La solución es dejar los _getter_ y los _setter_ solo para propiedades que no vayan a ser utlizadas por una vista (esto también afecta a los servicios, por si estamos haciendo algo con alguna propiedad de un servicio en la vista).
  
  **Referencias**:
  1. [Angular Performance: Optimize Template Expressions](https://blog.bitsrc.io/angular-performance-optimize-template-expressions-e30ac3f2ea7f).
  2. [10 Tricks to Optimize Your Angular App](https://blog.bitsrc.io/10-tricks-to-optimize-your-angular-app-44208f616bf0).
