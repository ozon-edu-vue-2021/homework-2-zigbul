<template>
    <li class="node-tree">
        <span 
            :class="['label', 
                    this.node.type === 'directory' && 'label_folder-style',
                    this.node.type === 'file' && 'label_file-style',
                    this.node.type === 'link' && 'label_link-style',
                    this.isClicked && 'label_active',
                    ]" 
            v-on:dblclick="toggleActive"
            v-on:click="toggleClicked"
        >
            {{node.name}}
        </span>

        <ul v-if="node.contents && node.contents.length && isActive">
            <node v-for="child in node.contents" :node="child" :key="child.name"></node>
        </ul>
    </li>
</template>

<script>

export default {
    name: "Node",
    data: function() {
        return ({
            isActive: false,
            isClicked: false,
        })
    },
    props: {
        node: Object,
    },
    methods: {
        toggleActive() {
            this.isActive = !this.isActive;
        },
        toggleClicked() {
            if (this.node.type !== 'directory') {
                this.isClicked = !this.isClicked;
            }
        }
    },
}
</script>

<style scoped>
    .label {
        padding-left: 20px;
        cursor: pointer;
    }

    .label_folder-style {
        background: url('../assets/folder.svg') no-repeat left center;
        font-weight: bold;
    }

    .label_file-style {
        background: url('../assets/file.svg') no-repeat left center;
        background-size: 20px;
    }

    .label_link-style {
        background: url('../assets/link.png') no-repeat left center;
        background-size: 20px;
        color: blue;
    }

    .label_active {
        background-color: aqua;
    }
</style>
