# MdSnackBar
`MdSnackBar` is a service, which opens snack bar notifications in the view.

### Methods

| Name |  Description |
| --- | --- |
| `open(message: string,<br>  actionLabel: string, config: MdSnackBarConfig): MdSnackBarRef<SimpleSnackBar>` | Creates and opens a simple snack bar noticiation matching material spec. |
| `openFromComponent(component: ComponentType<T>, config: MdSnackBarConfig): MdSnackBarRef<T>` | Creates and opens a snack bar noticiation with a custom component as content. |

### Config

| Key |  Description |
| --- | --- |
| `viewContainerRef: ViewContainerRef` | The view container ref to attach the snack bar to. |
| `role: AriaLivePoliteness = 'assertive'` | The politeness level to announce the snack bar with. |
| `announcementMessage: string` | The message to announce with the snack bar. |


### Example
The service can be injected in a component.
```ts
import { Component, ViewContainerRef } from '@angular/core';
import { MdSnackBar, MdSnackBarConfig } from '@angular/material/snack-bar/snack-bar';

@Component({
  selector: 'my-component'
  providers: [MdSnackBar]
})
export class MyComponent {

 constructor(
   private snackBar: MdSnackBar
   private viewContainerRef: ViewContainerRef
 ) {}

 failedAttempt() {
   let config = new MdSnackBarConfig(this.viewContainerRef);
   this.snackBar.open('It didn\'t quite work!', 'Try Again', config);
 }

}
```
