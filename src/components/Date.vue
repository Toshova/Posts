<template>
<div>
        <p><strong>Date: </strong>{{formattedDate}}</p>
        <p><strong>Time: </strong>{{formattedTime}}</p>
    </div>
</template>

<script>
export default {
        data() {
            return {
                currentDate: new Date(),
            }
        },
        computed: {
            formattedDate() {
                return this.currentDate.toLocaleDateString();
            },
            formattedTime() {
                return this.currentDate.toLocaleTimeString();
            },
        }
    }

</script>