# mw-datepicker-range

mw-datepicker-range is a AngularJS module that extend the ui-bootstrap's datepicker directive to allow a selection of a range.

## Requirements (tested in)
- Angular (v1.6.4)
- Bootstrap (v3.3.7)
- ui-bootstrap (v2.5.0) (atleast 'ui.bootstrap.datepicker', 'ui.bootstrap.datepickerPopup' and their dependencys)

## Install

You can install this package either with `npm` or with `bower`.

### npm

```shell
npm install mw-datepicker-range --save
```

### bower

```shell
bower install mw-datepicker-range --save
```

## Usage

Once the script is included in your html file, simply include the module in your app:
```javascript
angular.module('myApp', ['mw-datepicker-range']);
```
    

You can use the datepicker like always, if you want to have the range selection add 'mw-multi-select'.
It will work with the standart datepicker and with the datepicker popup
```html
<div class="col-md-6">
    <p class="input-group">
        <input type="text" class="form-control" ng-model="dt" mw-multi-select="selectedDates" uib-datepicker-popup="dd/MM/y" is-open="opened" datepicker-options="dateOptions"/>
        <span class="input-group-btn">
            <button type="button" class="btn btn-default" ng-click="open()"><i class="glyphicon glyphicon-calendar"></i></button>
        </span>
    </p>
</div>
```
    

'mw-multi-select' contains an array with all dates inside the selected range.
The viewValue is changed so that it will use the first and last Date from the array.
This module will use the ``customClass`` property of the `datepickeroptions` to add the class 'selected' to every date in the selected range, look into the example for more information.

Be aware of the fact that if you use the range selection the model is literally useless for you because it will only store the current clicked date.
If you want to use the selected range you can use either the full array or use the service to parse the array into an object with 'before' and 'after' property

```javascript
$scope.mwMultiSelectService.parse($scope.selectedDates, format);
```


## Demo

<a href='https://plnkr.co/edit/cQ2Dr48Ya8mKcgHnrg5W?p=preview' target='_blank'>View demo on Plunker</a>


## Tasklist 
- [ ] add documentation
- [X] nodejs, bower support
- [ ] fix spelling, grammar mistakes
- [ ] add second selection type