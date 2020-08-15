<template>
  <div @click="$emit('taskStateChanged', task)" 
    class="task":class="stateClass">
        <span @click.stop="$emit('taskDeleted', task)" class="close">x</span>
      <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
    props: {
        task: { type: Object, required: true}
    },
    computed: {
        stateClass() {
            return {
                pending: this.task.pending,
                done: !this.task.pending
            }
        }
    }
}
</script>

<style>
.task {
    position: relative;
    box-sizing: border-box;
    width: 150px;
    height:  150px;
    padding: 10px;
    border-radius: 8px;
    font-size: 2rem;
    font-weight: 300;
    cursor: pointer;
    user-select: none;
    display: flex;
    justify-content: center;
    align-items: center;
}

.pending {
    border-left: 12px solid rgb(255, 136, 0);
    background-color: orange;
}

.done {
    color: rgba(255, 255, 255, 0.384);
    border-left: 12px solid rgb(0, 128, 64);
    background-color: green;
    text-decoration: line-through;
}
.pending .close {
    background-color: rgb(0, 0, 0);
}

.done .close {
    background-color: rgb(0, 0, 0);
}
.close {
    position: absolute;
    right: 10px;
    top: 10px;
    font-size: 0.9rem;
    font-weight: 600;
    height: 20px;
    width: 20px;
    border-radius: 10px;
    display: flex;
    justify-content: center;

}
</style>