---
layout: post
title: "Component Life Cycle In React Js"
categories: Technology
author: "Dasun Madushan"
---

Each Component in react has several Life cycle methods.This life cycle can monitor and manipulate at three phases,The three phases are:-

- Mounting
- Updating
- Unmounting

### Mounting

Attaching Elements to the DOM Tree When Mounting there are several built in methods get called.

- Constructor()
- render()
- componentDidMount()

### Constructor()

Called before Mounting.We should call super(props) inside the constructor.The we can access the props.

Two purpose of Constructor:-

1. Initializing local state

2. Binding event handler methods

Constructor is the place where we can assign this.state directly.SetState should not been  called inside the constructor.

### render()

Render elements to the react DOM.
Actual Output of the component is shown to the user.
Every update of the state this render method will be called.

Render method return,

- React elements

- Array and Fragments

- PortalsString

- Numbers

### ComponentDidMount

componentDidMount calls after the component is mounted

This is the place where we can load data form the remote server

We can instantiate our http request here.

It is like a document.ready in jquery

### Updating

If there is a any change in props and state,component will be updated

At the updating.Two main method is called,

- render()

- componentDidUpdate()

### componentDidUpdate()

componentDidUpdate calls immediate when there is any change in state.

- render()

- Render method will be called always.

- It rewrites the dom when there is any changes in state.