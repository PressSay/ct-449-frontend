<script>
export default {
    props: {
        modelValue: { type: String, default: "" },
    },
    emits: ["submit", "update:modelValue"],
    methods: {
        updateModelValue(e) {
            this.$emits("update:modelValue", e.target.value);
        },
    },
    submit() {
        this.$emit("submit");
    },
}
</script>

<template>
    <div class="input-group">
        <input type="text" class="form-control" placeholder="Nhập thông tin cần tìm" :value="modelValue"
            @input="updateModelValue" @keyup.enter="submit" />
    </div>
    <div class="input-gorup-append">
        <button class="btn btn-outline-secondary" type="button" @click="submit">
            <i class="fas fa-search"></i> Tìm Kiếm
        </button>
    </div>
</template>