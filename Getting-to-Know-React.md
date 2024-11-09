**Lectures**

**

17/10 - Understanding React** 📚

1.  Why frameworks are required and what purpose react servers.
2.  State, Components and Re-rendering
3.  DOM APIs(createElement, appendChild etc.) + useState hook + props

p5Js editor(React Code Base) - <https://github.com/processing/p5.js-web-editor>

**NOTE**: React requires variables to be bound to state in order to track their changes. Re-renders are made on the basis of change in these states.

Topics - Components, HOCs(Wrapper Component) , Performance Improvement, Hooks

**Performance Improvement(Re-render minimisation) - **

1.  Maintain the state within the component itself. If that's not feasible, manage the state at the LCA node. This approach prevents re-rendering of other components whose state remains unchanged.
2.  Use Key attribute to help react identify list items. This helps to prevent re-rendering of already rendered list items.

📌 **Hooks -**

1.  useState - allows to add states in your component.
2.  useEffect - allows to trigger logic when component mounts or its state changes. 
3.  useMemo - allows to cache/memoize calculation results for heavy operations. Check here - <https://github.com/daYnas9/JSBox/blob/main/useMemo.jsx>
4.  useCallback - allows to cache functions. Sometimes functions are passed as prop to other components so if parent component re-renders then child also does even if the function passed is exactly same(due to referential inequality) so by using this hook we can kind of cache the function to prevent unnecessary re-renders of child components. (**NOTE**: We should be careful while using **useCallback** because of we don't pass required params to dependency array then the function would get cached forever and will not re-render even when required)
5.  useRef - allows to create references to DOM elements. React discourages use of getElement... functions because when using useRef(), the DOM is under React's control.  
6.  memo - react API which is used to cache components. Memo only re-renders component when props added component changes.

**NOTE:** Whenever a parent re-renders, its children are guaranteed to be re-rendered even if components props are unchanged. To improve performance or skip re-rendering of child components, we memoization components and functions which is done by useMemo and useCallback(kind of performance improvement hooks).