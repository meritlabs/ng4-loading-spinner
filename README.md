# ng4-loading-spinner

Angular 4/5/6 custom async loading spinner with two simple methods for your asychronous calls.
Custom loading template & loading text inputs are also available.

[![support](https://img.shields.io/badge/Support-Angular%206.x-brightgreen.svg)](https://angular.io/docs)
[![support](https://img.shields.io/badge/Support-Angular%205.x-brightgreen.svg)](https://angular.io/docs)
[![support](https://img.shields.io/badge/Support-Angular%204.x-brightgreen.svg)](https://v4.angular.io/docs)
[![David](https://img.shields.io/david/peer/webcomponents/generator-element.svg)]()
[![license](https://img.shields.io/github/license/mashape/apistatus.svg)]()

> [ Docs Link ](https://amitmahida92.github.io/ng4-loading-spinner)

> [Link to ng4-loading-spinner](https://www.npmjs.com/package/ng4-loading-spinner)

## Default Spinner Example

[Open Plunker](https://plnkr.co/edit/I3MoLhxz1NO9PVtMTiaH?p=preview)

## Custom Template Example

[Open Plunker](https://plnkr.co/edit/gX8uvP2hb7DiE8Hs0a1R?p=preview)

## Installation

`npm i ng4-loading-spinner@meritlabs/ng4-loading-spinner#dist --save`

## Description

> _You can override the css for your customized spinner._

> _You can also configure your own threshold to show spinner only for more expensive processes!_

> _Supports latest Angular v5.x_

> _Supports latest Angular v6.x_

> _Supports latest Angular cli v1.5.x_

> _Supports latest Angular cli v6.x_

## Build and deploy

> Checkout to dist branch

`git checkout dist`

> Grab fresh code from master

`git merge master`

> Install dependencies

`yarn`

> Build new version

`yarn build`

> Push new version to the dist branch

`git add . && git commit -m"Update" && git push`

## Usage

> Import module to your application master module

```javascript
import { Ng4LoadingSpinnerModule } from 'ng4-loading-spinner';
```

> Make an import entry as shown below

```javascript
imports: [Ng4LoadingSpinnerModule.forRoot()];
```

> Include spinner component to your root level component.

```html
<ng4-loading-spinner> </ng4-loading-spinner>
```

> Import `Ng4LoadingSpinnerService` to the component where you want to show the spinner.

```javascript
import { Ng4LoadingSpinnerService } from 'ng4-loading-spinner';
```

> Inject dependancy

```javascript
    constructor(
        private spinnerService: Ng4LoadingSpinnerService
    ) { }
```

> Use `show()` method to display the loading spinner.

```javascript
this.spinnerService.show();
```

> Use `hide()` method to hide the loading spinner once the processing is done.

```javascript
this.spinnerService.hide();
```

## Example

```javascript
this.spinnerService.show();
this.http.get(GLOBAL['CONFIG_URL']).subscribe(data => {
  this.spinnerService.hide();
});
```

## Custom template

> _[template]_ : Accepts HTML which generates the loading spinner. You can apply additional css to design your own spinner, or can just pass \*.gif image to show the loading spinner.

> _[loadingText]_ : Accepts a string to display the text while the loading process.

> _[zIndex]_ : Accepts a z-index css property for loading text.

> _[threshold]_ : Accepts time in milliseconds for threshold through which you can conditionally show the spinner only for expensive calls. _Default is 500 ms._

> _[timeout]_ : Accepts time in milliseconds to hide the spinner automatically. _Default is 5000 ms._

> default _[loadingText]_ text would be blank.

> app.component.html : both are optional if not provided default would be shown.

```html
<ng4-loading-spinner [threshold]="2000" [timeout]="4000" [template]="template" [loadingText]="'Please wait...'" [zIndex]="9999"></ng4-loading-spinner>
```

> [threshold]="2000" : This will show the loading bar for the only processes which will take time more 2 secs.

> app.component.ts

```javascript
template: string = `<img src="http://pa1.narvii.com/5722/2c617cd9674417d272084884b61e4bb7dd5f0b15_hq.gif" />`;
```

## License

MIT © [Amit Mahida](mailto:amit.mahida9292@gmail.com)
