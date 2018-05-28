# AngularJSExample

### Mac Address Formatter usage:

```html
<html ng-app="myApp">
  <head>
    <meta charset="utf-8">
    <title>Mac Address Formatter</title>
  </head>
  <body ng-controller="mainController">
    <form name="myForm">
      <input type="text" ng-pattern="ctrl.MAC_ADDRESS_REGEX"
      maxlength="17" name="macAddress" ng-required="true" ng-model="ctrl.macAddress" ng-model-options="{allowInvalid: true}"
      ng-change="ctrl.macAddress = (ctrl.macAddress | macAddressFormatter)">
      <div class="">
        Valid: {{myForm.macAddress.$valid}}
      </div>
  </form>
  </body>
```

```javascript
angular.module("myApp", ["component.form"])
  .controller("mainController", function($scope, MAC_ADDRESS_REGEX){
    $scope.ctrl = this;

    this.MAC_ADDRESS_REGEX = MAC_ADDRESS_REGEX;
  });
```
