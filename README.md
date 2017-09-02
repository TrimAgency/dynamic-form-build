# Angular dynamic form builder
A reactive forms module that dynamicly creates inputs based on a config object.

## Installation
Copy entire module into your projects, src folder. In the feature module that 
you need to use the dynamic form builder add ```DynamicFormModule```
to the imports array.

## Usage

Create a config object for your form.

In your component class add a property that will hold your 
config object and assign your config object to this property.

In your components template add the form builder component:
```<dynamic-form></dynamic-form>```
Optionally you can pass in a form title or image:
```<dynamic-form>
     <h1>My Custom Form</h1>
   </dynamic-form>
```

Pass the componet property to the config attribute of the 
dynamic form.


