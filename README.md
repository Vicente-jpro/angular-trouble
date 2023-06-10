# angular-trouble

#### Kill port 42000
```bash
sudo kill $(sudo lsof -t -i:4200)
```

### Generate model 

```bash
ng generate module --routing nomeModulo
```

### Generate component 

```bash
ng generate component nome-modulo/nomeComponent
```

### Generate service 

```bash
ng generate service nomeService
```

### Generate interceptor 

```bash
ng generate interceptor nameInterceptor
```

### Generate environments

```bash
ng generate environments
```
### Generate guard

```bash
ng generate guard nameAuthenticatedFile
```




# Errors
###  Error occurs in the template of component ServicoPrestadoFormComponent.
```html
    <form #servicoPrestadoForm="ngForm" (ngSubmit)="onSubimit()">
          <div class="mb-3">
            <label for="exampleFormControlInput1" class="form-label">Data</label>
            <input type="date" class="form-control" id="exampleFormControlInput1">
          </div>
          <div class="mb-3">
            <select class="form-select" aria-label="Default select example">
                <option selected>Seleciona um cliente</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
          </div>
          <div class="mb-3">
            <label for="exampleFormControlInput1" class="form-label">Valor</label>
            <input type="number" class="form-control" id="exampleFormControlInput1" placeholder="name@example.com">
          </div>
          <div class="mb-3">
            <label for="exampleFormControlTextarea1" class="form-label">Descrição</label>
            <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
          </div>
    </form> 
```
Solution:
```typescript
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms'; // -> Import form modulo to your route

import { ServicoPrestadoRoutingModule } from './servico-prestado-routing.module';
import { ServicoPrestadoFormComponent } from './servico-prestado-form/servico-prestado-form.component';



@NgModule({
  declarations: [
    ServicoPrestadoFormComponent
  ],
  imports: [
    CommonModule,
    FormsModule, // -> Import form modulo to your route
    ServicoPrestadoRoutingModule
  ],
  exports:[
    ServicoPrestadoFormComponent,
  ]
})
export class ServicoPrestadoModule { } 
```
