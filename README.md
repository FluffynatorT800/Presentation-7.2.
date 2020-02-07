# Presentation-7.2.
#React Advanced JSX

JSX is mark up language to write components created by Facebook. 
It appears similar to HTML, but allows the inclusion of JavaScript expressions via {}

```javascript 
div>
     <p>Homer eats {7 * 12} donuts/week.</p>
     <p>He also likes {randomFood()}!</p>
   </div>
   ```
 These JavaScript expressions can contain any valid JavaScript except if-else Functions.
 
 The ternary operator allows to check for a certain condition.
 IF the condition is met expression a.) is returnd ELSE expression b.)
 
 ```javascript
 const App = () => {
 return (
   <div>
     {
       condition()
         ? <p>expression a.)</p>
         : <h1>expression b.)</h1>
     }
   </div>
 )
};
```
These expressions can also be styles or classes.


The && operator usually combines two conditons. 
In JSX it allows to set a condition that has to be met, befor a certain pice of mark up code is displayed.

```javascript
 <div>
     {
       yourCodeIsRubbish() && (
         <div className="alert">
           Now I will tell you, your code is rubbish.
         </div>
       )
     }
   </div>
```
In general it is better to place more complex logic and math in a seperat function, which than can be called in the JSX.


#React State

The state is, well.. the state of a component.
To be clear the state of component can be subject to change,
either by user input or a change in the data coming from the server.
When either happens the component in question is renderd again, to reflect this change.

The state is an object, to initialize it the following can be used: 

```javascript
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

```
It is important to note that `this.state = {something}` should only be used in the constructor.
To modify the state outside of a constructor the `this.setState()` method should be used.

```javascript   
  tick() {
    this.setState({
      date: new Date()
    });
  }
```
