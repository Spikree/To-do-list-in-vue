<template>
    <div id="main">
        <h3>Add Task</h3>
        <label for="date">Date</label>
        <input type="date">

        <label for="Title">Title</label>
        <input type="text" v-model="taskTitle">

        <label for="Descripton">
            Description:
        </label>
        <textarea name="Description" id="description" cols="30" rows="10"></textarea>


        <div class="buttons">
        <button @click="$emit('added')">Add</button>
        <button @click="$emit('close')">Task Complete</button>
        </div>  
    </div>
</template>

<script>
    export default {
        name : 'AddTask',
        emits: ['close','added'],
        data() {
            return {
                taskTitle: ""
            };
        }
    }
</script>

<style>
    #main {
            background-color: #fff;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 300px;
            margin: 0 auto;
            justify-content: center;
        }

        h3 {
            font-size: 1.5rem;
            margin: 0 0 20px;
        }

        label {
            display: block;
            font-weight: bold;
        }

        input[type="date"],
        input[type="text"],
        textarea {
            width: 100%;
            padding: 8px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 3px;
            font-size: 1rem;
        }

        button {
            background-color: #007BFF;
            color: #fff;
            border: none;
            border-radius: 3px;
            padding: 10px 20px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }
        .buttons {
            display: flex;
            justify-content: space-between;
        }
</style>