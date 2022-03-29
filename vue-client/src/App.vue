<template>
    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
                <th>Occupation</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="item in data" :key="item.id">
                <td>{{ item.id }}</td>
                <td>{{ item.firstName + " " + item.lastName }}</td>
                <td>{{ item.occupation }}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    name: "App",
    data: () => {
        return {
            data: [],
            url: "/api/toons",
        };
    },

    async mounted() {
        const res = await fetch(this.url);
        this.data = await res.json();
    },
};
</script>

<style></style>
