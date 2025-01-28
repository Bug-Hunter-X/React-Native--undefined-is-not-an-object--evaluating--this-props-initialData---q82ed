# React Native: undefined is not an object (evaluating 'this.props.initialData')

This repository demonstrates a common React Native error: attempting to access `this.props` or state before a component has mounted.  The error message, "undefined is not an object (evaluating 'this.props.initialData')", typically arises when you try to use props within the `constructor` or before the component fully mounts.

## Problem

The issue occurs because the component's props aren't available until after the component has been mounted by React Native's rendering process.  Accessing them prematurely results in `undefined`.

## Solution

The best practice is to initialize state with default values in the constructor and then update the state using lifecycle methods such as `componentDidMount` once the props are available.  Alternatively, if data is needed for rendering, you can use a conditional render to avoid errors before props are ready.