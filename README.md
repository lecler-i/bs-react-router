# NOT READY

will eventually be [Reason](https://reasonml.github.io) bindings to [React Router](https://reacttraining.com/react-router/)

## Install

```bash
npm install --save bs-react-router
```

Then add bs-react-router to bs-dependencies in your bsconfig.json:

```bash
{
  ...
  "bs-dependencies": ["bs-react-router"]
}
```

## Example

```jsx
let component = ReasonReact.statelessComponent("App");
let blueStyle = ReactDOMRe.Style.make(~color="#000099", ());

let make = (_children) => {
    ...component,
    render: (_self) =>
        <div>
            <BrowserRouter>
                <div>
                    <NavLink _to="/">{ReasonReact.stringToElement("Home")}</NavLink>
                    <NavLink _to="/user" style=(blueStyle)>{ReasonReact.stringToElement("User")}</NavLink>

                    <Route path="/" exact=true component=(() => <HomePage />) />
                    <Route path="/user" component=(() => <UserPage />) />
                </div>
            </BrowserRouter>
        </div>
};
```