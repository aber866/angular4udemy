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

recipes: Recipe[] = []; //hemos declarado un array del model REcipe

<img src="{{ recipe.imagePath }}" [src]="recipe.imagePath" //es lo mismo

Para debuggear en chrome/sources/webpack/./src/app/ tenemos los typescript
Angular augury extension de chrome

@Input() delante de una propiedad o definicion es que es visible para los parent components
[element]="server" //property binding para por ej decir que server es de tipo element

EventEmitter, emit, @Output() //comunicacion entre componentes

//En el html podemos poner referencias #reference y usarlas solo en el html. Es todo el elemento html

//Para pasar parametros de un componente padre a uno hijo con *ngFor
	//En el listado
		<item *ngFor="let i of recipes" [recipe]="i"></item>
	//En el item ts
		@Input() recipe: Recipe;

//Para crear una directiva de atributo propia. En el ts
	@HostBinding("class.open") isOpen = false;
	@HostListener("click") name() {}

//Para inyectar un service en otro
	@Injectable()
	constructor(private counterService: CounterService) {}
	this.counterService.method() //en un metodo

//Router
	constructor(private router: Router){}
	this.router.navigate(['/servers'])
	<a [routerLink]="['/users', 10, 'Anna']">Load Anna (10)</a> //html // segundos parametros son los :

	// En app.module.ts o crear fichero import { AppRoutingModule } from './app-routing.module';
	const appRoutes: Routes = [ 
		{ path: '', component: HomeComponent },
		{ path: 'users/:id/:name', component: UserComponent }];

	<router-outlet></router-outlet> //para los nested components

//Observables
//handle the change of router parameters

//Forms
	import FormsModule in imports appmodule
	https://angular.io/api/forms/Validators
	https://angular.io/api?type=directive
	Se puede usar 0 binding con solo ngModel en el input, 1 way binding con [ngModel]="defaultQuestion" o two way binding con [(ngModel)]="answer"

//HTTP
	Los servicios Post, PUt devuelven un observable (http-final / server.services.ts). Esto es como promesas y hay que subscribirse, que seria un then. En el component
	this.serverService.storeServers(this.servers)
    .subscribe(
        (response) => console.log(response),
        (error) => console.log(error)
    );
















