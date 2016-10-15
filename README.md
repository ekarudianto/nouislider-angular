# This is a forked repository from
[Yankovsky nouislider angular directive](https://github.com/Yankovsky/nouislider-angular)

This is nouislider angular directive converted into module based so that it could have a es6 'import' syntax support.

# nouislider-angular

You could check the demo at Yankovsky website -> http://yankovsky.github.io/nouislider-angular/examples

You can pass any [nouislider options](http://refreshless.com/nouislider/slider-options/) options to ya-no-ui-slider directive.

## Installation

#### Install with NPM

```
npm install nouislider-angular-es6
```

## Basic usage

```javascript
import from 'nouislider-angular-es6';

angular.module('sampleApp', ['ya.nouislider'])
  .controller('SampleCtrl', function($scope) {
    $scope.options = {
        start: [20, 70],
        range: {min: 0, max: 100}
    }
});
```
```html
<div ya-no-ui-slider='options'></div>
```

## Options

#### Global config

You can set global configuration value yaNoUiSliderConfig and all nouislider options will inherit from it:

```javascript
angular.module('sampleApp', ['ya.nouislider'])
    .value('yaNoUiSliderConfig', {step: 1})
```

#### Event handlers

```javascript
$scope.eventHandlers = {
    update: function(values, handle, unencoded) {},
    slide: function(values, handle, unencoded) {},
    set: function(values, handle, unencoded) {},
    change: function(values, handle, unencoded) {}
}
```
```html
<div ya-no-ui-slider='options' 
     ya-no-ui-slider-events='eventHandlers'></div>
```

#### Disable slider or individual handlers

```html
<div ya-no-ui-slider='options' 
     ya-no-ui-slider-disabled='sliderDisabled'
     ya-no-ui-slider-handle1-disabled='handle1Disabled'
     ya-no-ui-slider-handle2-disabled='handle2Disabled'></div>
```

#### Slide event debounce

Use number to specify delay in ms or use special value "Infinity" to disable updating model on slide event.

```html
<div ya-no-ui-slider='options' 
     ya-no-ui-slider-slide-debounce='300'></div>
     
<div ya-no-ui-slider='options' 
     ya-no-ui-slider-slide-debounce='Infinity'></div>
```

### Setting range value example

Use number to specify the range to be reflected on the nouislider view

```html
<div ya-no-ui-slider='options'></div>
<button ng-click="ctrl.options.start = [40, 60]">set [40, 60]</button>
```

```javascript
import from 'nouislider-angular-es6';

angular.module('sampleApp', ['ya.nouislider'])
  .controller('SampleCtrl', function($scope) {
    $scope.options = {
        start: [20, 70],
        range: {min: 0, max: 100}
    }
});
```

## Building minified version

To build minified version use `npm run build` command.
