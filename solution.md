## Prevent-Multiple-Renders-in-React
application rendering component reslessly and finally crush the program or page not responding

think you use a  `console.log()` in your application and you noticing that console is rendering multiple time
```
const Home = () => {
  const { state: { products, error, loading } } = useProducts();
  console.log(products) // 
  return (
    <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 max-w-7xl gap-14 mx-auto my-10'>

    </div>
  );
}
```
the solution is to remove the `</React.StrictMode>` react strict mode in `index.js` file in root of the application. it work for me
```
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  // <React.StrictMode>
    <App />
  // </React.StrictMode>
);
```
