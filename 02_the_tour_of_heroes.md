## 02 The Tour of Heroes

### The application shell

- Components: Components are the fundamental building blocks of Angular applications. They display data on the screen, listen for user input, and take action based on that input.

- Use component element in html: `{{ title }}`

### Create a new component to display hero information

```
ng generate component heroes
```
The CLI creates a new folder, src/app/heroes/ and generates the three files of the HeroesComponent.

### Constructor
- only Initialize local varialbes to simple value
- **Don't** fetch date here

### ngOnInit
Use **ngOnInit()** for two main reasons:
  1. To perform complex initializations shortly after construction.
  2. To set up the component after Angular sets the input properties.

### Add a model

1. in 'src/app', create 'hero.ts'
```
export class Hero {
  id: number;
  name: string;
}
```

2. Add a reference in HeroesComponent
```
hero: Hero = {
  id: 1,
  name: 'Windstorm'
};
```

3. Use it in 'heroes.component.html'
```
<h2>{{hero.name | uppercase}} Details</h2>
```

### Two-way binding
Data flow from the component class out to the screen and from the screen back to the class

1. update 'heroes.component.html'
```
<div>
  <label>
    <input [(ngModel)]="hero.name" placeholder="name">
  </label>
</div>
```

2. open 'app.module.ts',  add **FormsModule** to the imports array

### Mock data
Create 'mock-heroes.ts' in the 'src/app/' folder. Define a **HEROES** constant as an array of ten heroes and export it.

### *ngFor
```
<h2>My Heroes</h2>
<ul class="heroes">
  <li *ngFor="let hero of heroes">
    <span class="badge">{{hero.id}}</span> {{hero.name}}
  </li>
</ul>
```

### Click event binding
```
<li *ngFor="let hero of heroes" (click)="onSelect(hero)">
```

in 'heroes.component.ts'
```
selectedHero: Hero;

onSelect(hero: Hero) {
  this.selectedHero = hero;
}
```
```
<h2>{{ selectedHero.name | uppercase }} Details</h2>
<div><span>id: </span>{{selectedHero.id}}</div>
<div>
  <label>name:
    <input [(ngModel)]="selectedHero.name" placeholder="name">
  </label>
</div>
```

### Class binding
Add and remove a CSS class conditionally: just add `[class.some-css-class]="some-condition"` to the element you want to style
```
[class.selected]="hero === selectedHero"
```