# angular4udemy
Udemy course from Angular 4

https://cli.angular.io/
npm install -g @angular/cli
npm install --save bootstrap

En .angular-cli.json metemos los estilos como boostrap

ng generate component servers = ng g c servers // Genera un nuevo componente

[(ngModel)]="name"
selector: '[app-servers]', //si ponemos corchetes es que es un atributo y no un elemento
							//dentro de @componentn en el js
selector: ".app-servers", // selector by class

ng-disabled="" ahora es [disabled]="!allowNewServer"
[] //Property binding () //event binding --> (click)=""
*ngIf="" //ng if
[ngStyle]="{backgroundColor: getColor()}" //Nueva para estilos
[ngClass]="{online: serverStatus === 'online'}" //ngclass

directivas con * es que cambian el dom

*ngFor="let server of servers" // creo que ngrepeat
