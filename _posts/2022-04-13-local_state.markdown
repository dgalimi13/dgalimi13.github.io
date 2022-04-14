---
layout: post
title:      "local state"
date:       2022-04-14 00:25:02 +0000
permalink:  local_state
---


My progression in React/Redux has been going well. Redux's ability to mange global state using a store has simplified a lot of my code with its ability to pass down state from parent to child components to be accessed as props. However, sometimes this method is overly complex and can actually complicate projects even further. In some situations I've found it more advantageous to use local state instead. The most common situation I've found myself using local state is with components responsible for rendering forms and accepting data through inputs. these components will often declare their initial local state as empty fields.

For instance:

state = {
    name: '', 
    population: ''
}

Through the use of events handlers utilizing .setState to detect changes, the value of local state for every alteration to the input fields like so:

handleChange = (event) => {
    this.setState({
        [event.target.name]: event.target.value
    })
}

When these event handlers are used as arguments to the redux event listener "onChange" event through the form input element below:

<input type='text' placeholder='Name' value={this.state.name} name="name" onChange={this.handleChange}/>

Every change to the input field will cause a change in the components local state and the value of state to be updated.

These components are not usually concerned with receiving state data from parent components ,they utilize local state strictly to respond to changes internally. 

I must further develop my knowledge of local state in order to pass my module 5 review. however, I feel I've made a large step forward in insuring that my projects are as DRY as possible with components that are maintaining proper separation  of concerns
