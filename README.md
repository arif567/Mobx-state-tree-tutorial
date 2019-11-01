Mobx State Tree
$npx create-react- app mobx-state-tree-tutorial –typescript 
Here –typescript is the plugin 
$Yarn  
Yarn to install dependencies 
$yarn add mobx mobx-react mobx-state-tree uuid
$ yarn add uuid 
$ yarn add @types/uuid -D
$ npm i expect
$ yarn run start

Sample Tree

import {types, Instance} from 'mobx-state-tree'
import { type } from 'os'

const EmployeeModel =types.model("Employee",{
    id:types.identifier,
    name:types.string,
    hours_worked:types.number
})

const EmployerModel=types.model("Employer",{
    id:types.integer,
    name:types.string,
    location:types.string,
    employees:types.array(EmployeeModel)
})

const RootModel=types.model("Root",{
    employer:EmployerModel
})

export {RootModel}

export type Root =Instance<typeof RootModel>
export type Employer =Instance<typeof EmployerModel>
export type Employee =Instance<typeof EmployeeModel>


