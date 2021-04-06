# VisualStudio Code

Es un editor altamente recomendado para la programación *front-end*, como es el caso de *Angular*, desarrollado por Microsoft, gratuito y de código abierto.

![VSCode](https://upload.wikimedia.org/wikipedia/commons/8/80/Visual_Studio_Code_0.10.1_on_Windows_7%2C_with_search.png)

Para descargar acceder a la web de [VisualStudio Code](https://code.visualstudio.com/).

## Extensiones

Las extensiones son añadidos al VisualStudio code que añaden funcionalidad adicional al editor.

Se recomienda instalar las siguientes extensiones:

* [Angular Essentials](https://marketplace.visualstudio.com/items?itemName=johnpapa.angular-essentials&wt.mc_id=angular_essentials-github-jopapa): Extensión que configura a VS Code para trabajar con la configuración estándar de **Angular**.
![Angular Essentials](https://johnpapa.gallerycdn.vsassets.io/extensions/johnpapa/angular-essentials/9.0.1/1581429463839/Microsoft.VisualStudio.Services.Icons.Default)
  
  Esta extensión en un set de otras extensiones que nos facilita el trabajo con Angular:
  * [Angular Snippets](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2&wt.mc_id=angularessentials-github-jopapa): esta extensión añade snippets de angular a VSCode. Para ver los accesos a los snippets acceder a la página de la extensión.
  * [Angular Language Service](#angularLanguageService): se explica [aquí](#angularLanguageService).
  * [Angular Console](https://marketplace.visualstudio.com/items?itemName=nrwl.angular-console&wt.mc_id=angularessentials-github-jopapa): Interfaz gráfica para la AngularCLI.
  * [Chrome Debugger](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome&wt.mc_id=angularessentials-github-jopapa): para debuguear desde el navegador Google Chrome.
  * [Edge Debugger](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge&wt.mc_id=angularessentials-github-jopapa):para debuguear desde el navegador Microsoft Edge (la versión sobre [chromium](https://www.chromium.org/)).
  * [Editor Config](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig&wt.mc_id=angularessentials-github-jopapa); configuración de editor a partir del fichero .editorconfig. Muy interesante para trabajo en equipo.
  * [ESlint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint&wt.mc_id=angularessentials-github-jopapa): Extensión para que nos muestre el lint en el código, siguiendo las reglas que se indiquen.
  * [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=pkief.material-icon-theme&wt.mc_id=angularessentials-github-jopapa): tema de iconos Material para los ficheros del proyecto.
  * [npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script&wt.mc_id=angularessentials-github-jopapa): esta extensión nos permite ejecutar las acciones del fihcero package.json en la barra lateral izquierda de VSCode.
  * [Peacock](https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock&wt.mc_id=angularessentials-github-jopapa): esta extensión nos permite configurar el proyecto para que se abra el VSCode de un color, de forma que si trabajamos con varios proyectos a la vez, cada uno tenga un color.
  * [Prettier](#prettier): se explica [aquí](#prettier).
  * [Winter is Coming](https://marketplace.visualstudio.com/items?itemName=johnpapa.winteriscoming&wt.mc_id=angularessentials-github-jopapa): tema visual para VSCode.

* [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint): Esta extensión nos subraya de amarillo y marca el fichero con error cuando hay un error en el lint del fichero.
![ESLint](https://dbaeumer.gallerycdn.vsassets.io/extensions/dbaeumer/vscode-eslint/2.1.19/1615820719164/Microsoft.VisualStudio.Services.Icons.Default)

* [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2): Esta extensión nos colorea de distinto color las llaves, paréntesis y corchetes para así saber si los estamos cerrando bien cuando los tenemos anidados.
![Bracket Pair Colorizer 2](https://github.com/CoenraadS/Bracket-Pair-Colorizer-2/raw/master/images/example.png)

* [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph): Muestra el gráfico del repositorio de Git en una ventana de VSCode.
![Git Graph](https://github.com/mhutchie/vscode-git-graph/raw/master/resources/demo.gif)

* <a name="angularLanguageService"></a>[Angular Language Service](https://marketplace.visualstudio.com/items?itemName=Angular.ng-template): Esta extensión hace que se pueda acceder desde la vista a las propiedades, métodos y servicios públicos de la clase del Componente.
![Angular Language Service GIF](https://github.com/angular/vscode-ng-language-service/raw/master/demo.gif)

* [i18n Ally](https://marketplace.visualstudio.com/items?itemName=lokalise.i18n-ally): Esta extensión nos ayuda a la hora de realizar las traducciones del sito que estamos desarrollando, permitiendo buscar directamente la traducción en Goolge Translator.
![i18n Ally](https://github.com/antfu/i18n-ally/blob/screenshots/review-editor.png?raw=true)

* <a name="prettier"></a>[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode): Estandarización del código.
![Prettier](https://miro.medium.com/max/600/0*_wpeJb8N1Z2KgVMj.)

* [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight): esta estensión nos marca los textos `TODO:` y `FIXME:` en el código.
![TODO Highlight](https://raw.githubusercontent.com/wayou/vscode-todo-highlight/master/assets/material-night-eighties.png)

* [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics): esta estensión nos indica la _Complejidad Ciclomática_ de las funciones.
![CodeMetrics](https://raw.githubusercontent.com/kisstkondoros/codemetrics/master/images/metric_details.png)

* [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens): Con esta extensión podemos ver en el PR se ha subido las modificaciones de código dentro del código.
![GitLens](https://raw.githubusercontent.com/eamodio/vscode-gitlens/master/images/docs/code-lens.png)

* [SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarlint-vscode): Con esta extensión podemos pasar las reglas del servidor de sonarqube sin necesidad de hacer un push del commit, además si configuramos las reglas, nos avisa dentro del código de issues que se van a generar en el sonarqube.
![SonarLint](https://github.com/SonarSource/sonarlint-vscode/raw/master/images/sonarlint-vscode.gif)

* [Draw.io](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio): Este plugin no es oficial, pero nos integra la aplicación [Draw.io](https://app.diagrams.net/) dentro de Visualstudio Code. Con esto tenemos que si abrimos un fichero _.drawio_ nos muestra el editor del Draw.io
![Draw.io](https://github.com/hediet/vscode-drawio/raw/master/docs/demo.gif)

* [Terminal] (https://marketplace.visualstudio.com/items?itemName=formulahendry.terminal): Esta extensión es muy sencilla, pone un icono para abrir o cerrar la terminal integrada de Visualstudio Code.
   ![Terminal Extension](https://github.com/formulahendry/vscode-terminal/raw/master/images/toggle.png).

* [Jest](https://marketplace.visualstudio.com/items?itemName=Orta.vscode-jest): Esta extensión es muy recomendable para trabajar con Jest, nos marca los test que pasan o fallan, y marca el _expect_ que da el error.

  ![Jest](https://orta.gallerycdn.vsassets.io/extensions/orta/vscode-jest/3.2.0/1588254430761/Microsoft.VisualStudio.Services.Icons.Default)

## Shortkeys

* [Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf).

* [macOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf).

* [Linux](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf).

## Cursos

* [Visual Studio Code: Mejora tu velocidad para codificar](https://www.udemy.com/course/vscode-mejora-tu-velocidad-para-codificar/).

___
Desarrollado por:

Juan Antonio Moreno Valderrama.

<a href="https://twitter.com/jmorenovade"><img src="https://img.shields.io/twitter/follow/jmorenovalde?label=Twitter&style=social" alt="Twitter"></a>
<a href="https://www.linkedin.com/in/juan-antonio-moreno-valderrama/"><img src="https://img.shields.io/badge/LinkedIn--_.svg?style=social&logo=linkedin" alt="LinkedIn"></a>
<a href="https://github.com/jmorenovalde"><img alt="GitHub followers" src="https://img.shields.io/github/followers/jmorenovalde?style=social"></a>
