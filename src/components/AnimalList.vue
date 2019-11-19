<template>
    <div>
        <h1>Animal List</h1>

    <table id="animals">
        <tr>
            <th>Species</th>
            <th>Name</th>
            <th>Date of Birth</th>
        </tr>

        <tr v-for="(animal, key) in animals" :key="key">
            <td>{{ animal.species}}</td>
            <td>{{ animal.name}}</td>
            <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'Nepoznat' }}</td>
            <td>
                <button @click="removeAnimal(key)">Remove Animal</button>
            </td>
             <td v-if="key > 0">
                <button @click="moveToTop(key)">Move to Top</button>
            </td>
        </tr>
    </table>    
    </div>
</template>

<script>
import moment from 'moment'
export default {
    data() 
    {
        return {
            animals: [
                {species: "Lion", name: "Sinba", dateOfBirth: moment().format("DD-MM-YYYY")},
                {species: "Dog", name: "Pica", dateOfBirth: ''},
                {species: "Cat", name: "Bica", dateOfBirth: moment().format("DD-MM-YYYY")},
                {species: "Tiger", name: "Ica", dateOfBirth: ''},
                {species: "Monkey", name: "Mica", dateOfBirth: moment().format("DD-MM-YYYY")},
            ],
        }
    },
    methods: {
        removeAnimal(key){
            this.animals.splice(key, 1);
        },

        moveToTop(key){
            if (key > 0){
            let toTop = this.animals[key];       
            this.animals.splice(key, 1);
            this.animals.unshift(toTop);    
            }
        }
        

    }

}
</script>

<style scoped>
    td {
        border:1px solid black;
        padding: 3px;
    }
</style>