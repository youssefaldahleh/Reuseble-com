<template>
    <span :class="[loading ? 'loading' : '']"></span>
    <button v-if="this.loading === false" :class="[
        variant,
        sizeClass,
        loading,
        roundedClass,
        disabled ? (disabled = 'disabled') : 'visible',
        block ? (block = 'block') : '',
    ]" :style="[
    'color:' + color,
    'border-color:' + color,
    'background-color:' + bkcolor,
]">
        <slot name="prepend"></slot>
        <slot>{{ buttonText }}</slot>
        <slot name="append"></slot>
    </button>
</template>
<script>
let colortest = "red";

export default {
    props: {
        color: {
            type: String,
            default: "withe",
        },
        bkcolor: {
            type: String,
            default: "rgb(13, 73, 202);",
        },
        buttonText: {
            type: String,
            default: "Button",
        },
        variant: {
            type: String,
            default: "flat",
        },
        buttonSize: {
            type: String,
            default: "regular",
        },
        rounded: {
            type: String,
            default: "medium",
        },
        disabled: {
            type: Boolean,
            default: false,
        },
        block: {
            type: Boolean,
            default: false,
        },
        loading: {
            type: Boolean,
            default: false,
        },
    },
    computed: {
        sizeClass() {
            switch (this.buttonSize) {
                case "small":
                    return "small-size";
                    break;
                case "large":
                    return "large-size";
                    break;
                case "regular":
                    return "regular-size";
                    break;
            }
        },
        roundedClass() {
            switch (this.rounded) {
                case "small":
                    return "small-round";
                    break;
                case "large":
                    return "large-round";
                    break;
                case "medium":
                    return "medium-round";
                    break;
            }
        },
        isLoading() {
            if (this.loading) {
                this.disabled === true;
            }
        },
    },
};
</script>

<style scoped>
button {
    border: none;
    cursor: pointer;
}

.elevated {
    color: white;
    box-shadow: 0px 2px 8px rgba(0, 0, 0, 1.30);
}

.flat {
    color: white;
}

.outlined {
    border: 1px solid rgb(13, 73, 202);
    color: rgb(13, 73, 202);

}

.text {
    color: rgb(13, 73, 202);
}

.regular-size {
    padding: 10px;
}

.small-size {
    padding: 5px;
}

.large-size {
    padding: 15px;
}

.small-round {
    border-radius: 2px;
}

.medium-round {
    border-radius: 4px;
}

.large-round {
    border-radius: 8px;
}

.disabled {
    visibility: hidden;
}

.visible {
    visibility: visible;
}

.block {
    width: 100%;
}

@keyframes spinner {
    to {
        transform: rotate(360deg);
    }
}

.loading:before {
    content: "";
    margin-top: 10px;
    margin-left: 10px;
    box-sizing: border-box;
    position: absolute;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 2px solid #ccc;
    border-top-color: #000;
    animation: spinner 0.6s linear infinite;
}
</style>
