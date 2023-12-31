# Customer Portal Project

Welcome to the README for our Customer Portal project that utilizes React for building various applications and packages. This repository is organized using npm Workspaces and nx to manage multiple packages within a single repository.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
<!-- - [Available Scripts](#available-scripts) -->
<!-- - [Contributing](#contributing) -->
<!-- - [License](#license) -->

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- Node.js: [Download and Install Node.js](https://nodejs.org/)
- Npm: [Install Npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- Git: [Download and Install Git](https://git-scm.com/)
- NX: [Install Nx](https://nx.dev/getting-started/installation)
- Tailwind: [Install Nx Tailwind](https://nx.dev/recipes/react/using-tailwind-css-in-react)
- React-Redux: [Install React-Redux](https://nx.dev/packages/react/generators/redux)
- Redux-Saga: [Install Redux Saga](https://nx.dev/packages/react/generators/redux)
- Axios: [Install Axios](https://www.npmjs.com/package/axios)
- Yup: [Install Yup For validation schema](https://www.npmjs.com/package/yup)
- Formik: [Install Formik Form Handling](https://formik.org/)


## Project Structure

[/apps/](https://nx.dev/concepts/more-concepts/monorepo-nx-enterprise) contains the application projects. This is the main entry point for a runnable application. We recommend keeping applications as light-weight as possible, with all the heavy lifting being done by libraries that are imported by each application.

  - Each application hold core business logic.
  - Create Pages and communicate with store.
  - Import Common components and always try to reuse component.
  - Try to use tailwind styling, if and but needed create .scss for custom syting.
  - Take care of component rerendering and use below core react concepts :
    - [useCallback](https://react.dev/reference/react/useCallback) (The useCallback is a react hook that returns a memoized callback when passed a function and a list of dependencies as parameters. It’s very useful when a component is passing a callback to its child component to prevent the rendering of the child component. It only changes the callback when one of its dependencies gets changed).
    
    - [useMemo](https://react.dev/reference/react/useMemo) (The useMemo is similar to useCallback hook as it accepts a function and a list of dependencies but it returns the memoized value returned by the passed function. It recalculated the value only when one of its dependencies change. It is useful to avoid expensive calculations on every render when the returned value is not going to change.) ```
  
[/libs/](https://nx.dev/concepts/more-concepts/creating-libraries) contains the library projects. There are many kinds of libraries, and each library defines its own external API so that boundaries between libraries remain clear.

  - Create All Common Components as library
    - Ex : Button, Input, Text Editor, HTML Parser, Table, Pagination, Search Input, Accordian, Modal
  - Create Redux Store as a library
    - Create Separate Library for Each Application with Actions, Reducers, Store, Generator Functions 
    
[/tools/](#tools) contains scripts that act on your code base. This could be database scripts, local executors, or local generators.

[/nx.json](#nxjson) configures the Nx CLI itself. It tells Nx what needs to be cached, how to run tasks etc.

[/tsconfig.base.json](tsconfig) sets up the global TypeScript settings and creates aliases for each library to aid when creating TS/JS imports.

### customer-portal/ <br/>
├── apps/ (Multiple Applications Under This Folder)<br/>
├──── insta-pasa/ <br/>
├──────── src/ <br/>
├─────────── app/ (All business modules) <br/>
├─────────── assets/ (All static assets) <br/>
├─────────── environments/ (Environment specific values) <br/>
├── #libs/<br/>
├── #tools/<br/>
├── #nx.json<br/>
├── #package.json<br/>
└── #tsconfig.base.json<br/>


