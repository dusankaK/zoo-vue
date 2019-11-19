<template>
    <div>
        <h1>Animal List</h1>

    <table>
        <tr>
            <th>Species</th>
            <th>Name</th>
            <th>Date of Birth</th>
        </tr>

        <tr v-for="(animal, key) in animals" :key="key">
            <td>{{ animal.species}}</td>
            <td>{{ animal.name}}</td>
            <td>{{ animal.dateOfBirth}}</td>
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
                {species: "Dog", name: "Pica", dateOfBirth: moment().format("DD-MM-YYYY")},
                {species: "Cat", name: "Bica", dateOfBirth: moment().format("DD-MM-YYYY")},
                {species: "Tiger", name: "Ica", dateOfBirth: moment().format("DD-MM-YYYY")},
                {species: "Monkey", name: "Mica", dateOfBirth: moment().format("DD-MM-YYYY")},
            ],
        }
    }

}
</script>

<style scoped>

</style>