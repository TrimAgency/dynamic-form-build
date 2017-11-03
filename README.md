# Angular dynamic form builder
A reactive forms module that dynamicly creates inputs based on a config object.

## Installation
Copy entire module into your projects, src folder. In the feature module that 
you need to use the dynamic form builder add ```DynamicFormModule```
to the imports array.

## Usage

#### Create a config object for your form.
```
export const formConfig = [
      {
        type: 'input',
        inputType: 'text',
        name: 'name',
        value: 'bob',
        placeholder: 'Enter your name',
        validators: [
          Validators.required
        ]
      },
      {
        type: 'select',
        name: 'county',
        value: null,
        options: [ { label: 'broward', value: 'broward' }, { label: 'maimi-dade', value: 'maimi-dade' } ],
        placeholder: 'Select a county',
        validators: [
          Validators.required
        ]
      },
      {
        label: 'Submit',
        name: 'submit',
        type: 'button',
        disabled: true
      }
    ];
```
Note: Input type 'select', pass a value of null for placeholder to work.  This is a known issue with Angular 2.

#### In your component class add a property that will hold your config object and assign your config object to this property.
If you would like to add type checking to your property, import the Config interface from the models folder in the dynamic form builder module
```
export class SomeComponent {
   config: Config[] = formConfig
// rest of component
```

#### In your components template add the form builder component:
```<dynamic-form></dynamic-form>```

#### Optionally you can pass in a form title or image:
```
<dynamic-form>
   <h1>My Custom Form</h1>  // projected content
</dynamic-form>
```

#### Pass the componet property to the config attribute of the dynamic form:
```
<dynamic-form [config]="config">
   <h1>My Custom Form</h1>  // projected content
</dynamic-form>
```

#### Bind an event handler that listens for the submitted event form the dynamic form:
```
<dynamic-form 
   [config]="config"
    // submitted is the event emitted
    (submitted)="myHandlerFunction($event)"> 
   <h1>My Custom Form</h1>  // projected content
</dynamic-form>
```


