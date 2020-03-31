<template>
<v-container>
    {{todoList}}
    <v-layout row wrap>
        <v-flex xs6>
            <List/>
        </v-flex>
        <v-flex xs6>
            <ListAdd
                @listAdd="listAdd"
            />
        </v-flex>
    </v-layout>
</v-container>
</template>

<script>
import List from './List'
import ListAdd from './ListAdd'

export default {
    components: {
        List,
        ListAdd
    },
    data() {
        return {
            todoList: ["투두리스트를 입력하세요"]
        }
    },
    methods: {
        listAdd(memo) {
            console.log("recieve!" + memo)
            this.todoList.push({memo: memo, status: 'created'})
        }
    }
}
</script>