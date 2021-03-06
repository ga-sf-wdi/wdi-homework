# Angular Directives

Angular is made up of directives that supercharge your html. Some of them you already know like `ng-app`, `ng-click`, `ng-controller`, and `ng-model`. You can also make your own custom directives, but Angular also ships with a slew of very useful ones. To understand Angular directives better, lets look at some of the basic "native" Angular directives.

**Follow Along** - please create a basic angular project in an `index.html` page and follow along with these examples by copying them into your code and trying them out.

## Hiding and Showing

#### `ng-show`
(Hint: use `ng-init` to set a variable upon initialization)
```html
<div ng-init="current_user = { name: 'bob' }"></div>

<div ng-show="current_user">
  {{current_user.name}}
</div>
```

#### `ng-hide`
```html
<div ng-hide="its_nighttime">
  Good Night!
</div>
```


## ng-pluralize

This directive lets you pluralize nouns based on a dynamic `count` variable or expression.

```html
<ng-pluralize count="personCount"
                 when="{'0': 'Nobody is viewing.',
                     'one': '1 person is viewing.',
                     'other': '{} people are viewing.'}">
</ng-pluralize>
```

```
Nobody is viewing
1 person is viewing
4 people are viewing
```

## Validation

Angular gives you some easy to use form validations if you use the `ng-submit` and the `ng-disabled` directives. `ng-submit` lets you add inline validators like `required` and `ng-minlength` and `ng-maxlength`.

```html
<div class="row">
  <div class='col-sm-4 col-sm-4-offset'>
    <form name="login_form" ng-submit="login()">
      <div class='form-group'>
        <label>Email</label>
        <input class='form-control' type="email" placeholder="Email" name="email" ng-model="user.email" required>
      </div>
      <div class="form-group">
        <label>Password</label>
        <input class='form-control' type="password" placeholder="Password" name="password" ng-model="user.password" ng-minlength=6 required />
      </div>
      <button class='btn btn-primary' type="submit" ng-disabled="login_form.email.$invalid || login_form.password.$invalid">Login</button>
    </form>
  </div>
</div>
```

## Filters

Angular gives you a handful of standard [filters](https://docs.angularjs.org/api/ng/filter).

#### `currency`
Formats a number as a currency (ie $1,234.56). When no currency symbol is provided, default symbol for current locale is used.

```js
{{amount | currency}}
// $1,234.56
```


#### `date`

```js
{{'1288323623006' | date:"MM/dd/yyyy 'at' h:mma"}}
// 10/28/2010 at 8:40PM
```

#### `filter`

A standard filter lets you dynamically filter `ng-repeat` lists. Let's look at the syntax.

The below code outputs a list of people with their phone numbers that we can filter by a search input. The `ng-init` directive initializes the template with the array of data (this is not normally done! Usually this data would come from a controller). The `searchText` variable in $scope becomes our filter in the `ng-repeat` directive.

```html
<div ng-init="friends = [{name:'John', phone:'555-1276'},
                         {name:'Mary', phone:'800-BIG-MARY'},
                         {name:'Mike', phone:'555-4321'},
                         {name:'Adam', phone:'555-5678'},
                         {name:'Julie', phone:'555-8765'},
                         {name:'Juliette', phone:'555-5678'}]"></div>

<label>Search: <input ng-model="searchText"></label>

<table>
  <tr>
    <th>Name</th>
    <th>Phone</th>
  </tr>
  <tr ng-repeat="friend in friends | filter:searchText">
    <td>{{friend.name}}</td>
    <td>{{friend.phone}}</td>
  </tr>
</table>
```
