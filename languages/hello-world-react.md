# Hello World react

## Prerequisites
* Just a browser

## Steps
1. open [codepen.io](https://codepen.io) and create a pen
2. open the settings and add react plus react-dom as libs, as a preprocessor choose babel
3. add the following snippet as html
    ```
    <div id="app"></div>
    ```
4. add the following snippet as css
    ```
    .person {
        display: inline-block;
        margin: 10px;
        border: 1px solid #eee;
        box-shadow: 0 2px 2px #ccc;
        width: 200px;
        padding: 20px;
    }
    ```
5. add the following snippet as javascript
    ```
    function Person(props) {
    return (
        <div className="person">
        <h1>{props.name}</h1>
        <p>Your Age:  {props.age}</p>
        </div>
    );
    }

    var app = (
    <div>
        <Person name="Hannes" age="30"/>
        <Person name="Hans" age="40"/>
    </div>
    );

    ReactDOM.render(app, document.querySelector('#app'));
    ```