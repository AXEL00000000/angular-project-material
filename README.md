## Angular Material

Este repositorio contiene ejemplos de uso de diversos componentes de Angular Material, cada uno implementado en su propio componente con selector correspondiente. A continuación se presenta la estructura del README, que explica el propósito y funcionamiento de cada componente:

### 1. `<app-mat-autocomplete>`

**Descripción:**
Ejemplo de campo de texto con autocomplete utilizando `MatAutocompleteModule`. Permite al usuario filtrar y seleccionar opciones dinámicamente.

**Puntos clave del código:**

* Importación de `MatAutocompleteModule`, `MatInputModule` y `ReactiveFormsModule`.
* Uso de un `FormControl` para capturar el valor del input.
* Filtrado de opciones en tiempo real mediante un método `filter()`.
* En el template, se enlaza el `matAutocomplete` al input para desplegar la lista.

```html
<mat-form-field>
  <input matInput [formControl]="myControl" [matAutocomplete]="auto">
  <mat-autocomplete #auto="matAutocomplete">
    <mat-option *ngFor="let option of filteredOptions | async" [value]="option">
      {{option}}
    </mat-option>
  </mat-autocomplete>
</mat-form-field>
```

---

### 2. `<app-badge>`

**Descripción:**
Demostración de `MatBadgeModule` para mostrar notificaciones o contadores sobre un elemento.

**Puntos clave:**

* Importación de `MatBadgeModule`.
* Uso de la directiva `matBadge` con atributos como `matBadgeColor`, `matBadgePosition`.

```html
<button mat-raised-button matBadge="4" matBadgeColor="accent">
  Bandeja de mensajes
</button>
```

---

### 3. `<app-bottomsheet>`

**Descripción:**
Implementación de un bottom sheet deslizable usando `MatBottomSheetModule`.

**Puntos clave:**

* Inyección de `MatBottomSheet` en el constructor.
* Llamada a `open()` para desplegar un componente de contenido.
* Uso de un componente secundario para la plantilla del sheet.

```ts
openBottomSheet(): void {
  this.bottomSheet.open(BottomSheetOverviewComponent);
}
```

---

### 4. `<app-button>`

**Descripción:**
Ejemplos de botones estilizados con `MatButtonModule`.

**Puntos clave:**

* Importación de `MatButtonModule`.
* Clases como `mat-primary`, `mat-accent`, y variantes `raised`, `stroked`, `flat`, `icon`.

```html
<button mat-raised-button color="primary">Primary</button>
<button mat-stroked-button color="accent">Accent Stroked</button>
<button mat-icon-button><mat-icon>home</mat-icon></button>
```

---

### 5. `<app-buttontoggle>`

**Descripción:**
Ejemplo de `MatButtonToggleModule` para botones mutualmente exclusivos o multiselección.

**Puntos clave:**

* Uso de `mat-button-toggle-group` con `multiple` opcional.
* Enlace de valor mediante `ngModel` o `FormControl`.

```html
<mat-button-toggle-group name="fontStyle" aria-label="Font Style">
  <mat-button-toggle value="bold">Bold</mat-button-toggle>
  <mat-button-toggle value="italic">Italic</mat-button-toggle>
</mat-button-toggle-group>
```

---

### 6. `<app-card>`

**Descripción:**
Uso de `MatCardModule` para mostrar contenido en tarjetas con imagen, título y acciones.

**Puntos clave:**

* Componentes `<mat-card>`, `<mat-card-header>`, `<mat-card-content>`, `<mat-card-actions>`.

```html
<mat-card>
  <mat-card-header>
    <mat-card-title>Título de la tarjeta</mat-card-title>
  </mat-card-header>
  <img mat-card-image src="assets/image.jpg" alt="Imagen">
  <mat-card-content>Descripción breve.</mat-card-content>
  <mat-card-actions>
    <button mat-button>ACCION</button>
  </mat-card-actions>
</mat-card>
```

---

### 7. `<app-checkbox>`

**Descripción:**
Componente de casilla de verificación con `MatCheckboxModule`.

**Puntos clave:**

* Importación de `MatCheckboxModule`.
* Uso de `ngModel` para enlazar el estado.

```html
<mat-checkbox [(ngModel)]="isChecked">Aceptar términos</mat-checkbox>
```

---

### 8. `<app-chips>`

**Descripción:**
Ejemplo de `MatChipsModule` para etiquetas interactivas.

**Puntos clave:**

* Configuración de `MatChipInput` para agregar o eliminar chips.
* Uso de `mat-chip-list` y `mat-chip`.

```html
<mat-form-field>
  <mat-chip-list #chipList>
    <mat-chip *ngFor="let fruit of fruits" [selectable]="selectable"
              [removable]="removable" (removed)="remove(fruit)">
      {{fruit}}
      <mat-icon matChipRemove *ngIf="removable">cancel</mat-icon>
    </mat-chip>
    <input placeholder="New fruit..." [matChipInputFor]="chipList"
           (matChipInputTokenEnd)="add($event)">
  </mat-chip-list>
</mat-form-field>
```

---

### 9. `<app-dialog>`

**Descripción:**
Implementación de `MatDialogModule` para abrir cuadros de diálogo modales.

**Puntos clave:**

* Inyección de `MatDialog` en el componente.
* Apertura de un componente de diálogo con `open()`.
* Captura de respuesta con `afterClosed()`.

```ts
const dialogRef = this.dialog.open(DialogOverviewExampleDialog, {
  width: '250px',
  data: {name: this.name}
});

dialogRef.afterClosed().subscribe(result => {
  console.log('El diálogo cerró con:', result);
});
```

---

### 10. `<app-divider>`

**Descripción:**
Uso de `MatDividerModule` para separar contenido con líneas horizontales o verticales.

**Puntos clave:**

* Componente `<mat-divider>` con atributos `vertical`, `inset`.

```html
<mat-divider></mat-divider>
<mat-divider vertical></mat-divider>
```

---

### 11. `<app-icon>`

**Descripción:**
Ejemplo de `MatIconModule` para mostrar iconos SVG o ligas de Material Icons.

**Puntos clave:**

* Registro de iconos personalizados si es necesario.
* Uso de `<mat-icon>` con nombre de icono.

```html
<mat-icon>home</mat-icon>
<mat-icon svgIcon="custom_icon"></mat-icon>
```

---

### 12. `<app-gridlist>`

**Descripción:**
Demostración de `MatGridListModule` para crear layouts grid responsivos.

**Puntos clave:**

* Configuración de `cols`, `rowHeight`, `gutterSize`.
* Uso de `<mat-grid-tile>` para cada celda.

```html
<mat-grid-list cols="3" rowHeight="100px">
  <mat-grid-tile *ngFor="let tile of tiles">{{tile.text}}</mat-grid-tile>
</mat-grid-list>
```

---

### 13. `<app-datepicker>`

**Descripción:**
Uso de `MatDatepickerModule` junto con `MatInputModule` para selección de fechas.

**Puntos clave:**

* Importar `MatDatepickerModule`, `MatNativeDateModule`.
* Asignar `[matDatepicker]` al input y usar `<mat-datepicker>`.

```html
<mat-form-field>
  <input matInput [matDatepicker]="picker">
  <mat-datepicker-toggle matSuffix [for]="picker"></mat-datepicker-toggle>
  <mat-datepicker #picker></mat-datepicker>
</mat-form-field>
```

---

### 14. `<app-panel>`

**Descripción:**
Ejemplo de `MatExpansionModule` para paneles expandibles.

**Puntos clave:**

* Uso de `<mat-accordion>` y `<mat-expansion-panel>`.

```html
<mat-accordion>
  <mat-expansion-panel *ngFor="let item of items">
    <mat-expansion-panel-header>
      <mat-panel-title>{{item.title}}</mat-panel-title>
    </mat-expansion-panel-header>
    <p>{{item.content}}</p>
  </mat-expansion-panel>
</mat-accordion>
```

---

### 15. `<app-table>`

**Descripción:**
Implementación de `MatTableModule` para mostrar datos en tabla con paginación y ordenamiento.

**Puntos clave:**

* Configuración de `MatTableDataSource`, `MatPaginator`, `MatSort`.
* Definición de columnas en el componente y template.

```html
<table mat-table [dataSource]="dataSource" matSort>
  <!-- Definición de columnas -->
  <ng-container matColumnDef="position">
    <th mat-header-cell *matHeaderCellDef mat-sort-header>No.</th>
    <td mat-cell *matCellDef="let element">{{element.position}}</td>
  </ng-container>
  
  <tr mat-header-row *matHeaderRowDef="displayedColumns"></tr>
  <tr mat-row *matRowDef="let row; columns: displayedColumns"></tr>
</table>
<mat-paginator [pageSizeOptions]="[5, 10, 20]"></mat-paginator>
```

---

## imagenes

<img width="1910" height="883" alt="image" src="https://github.com/user-attachments/assets/544a5b0d-380a-4572-8e55-10d0130e4101" />
<img width="1915" height="863" alt="image" src="https://github.com/user-attachments/assets/a838b60b-7889-43fd-9e12-f67b33ea373a" />
<img width="1919" height="572" alt="image" src="https://github.com/user-attachments/assets/114a3eae-f8c6-4aef-a720-68044e855dbc" />
<img width="1905" height="607" alt="image" src="https://github.com/user-attachments/assets/b9265270-4460-4e6f-8301-2e0254fac93e" />
<img width="1899" height="812" alt="image" src="https://github.com/user-attachments/assets/7713bf39-5a8f-4e8a-9fdf-e2f8535e1414" />




