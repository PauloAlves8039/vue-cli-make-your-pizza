<template>
    <div class="container-pagination">
        <nav aria-label="Page navigation example">
            <ul class="pagination">
                <li class="page-item" @click="getPreviousPage()">
                    <a class="page-link" href="#">
                        <i class="bi bi-chevron-left iten-navigation"></i>
                    </a>
                </li>
                <li class="page-item" v-for="(pages, index) in totalPages" :key="index" @click="getDataPage(pages)">
                    <a class="page-link" href="#">
                        {{ pages }}
                    </a>
                </li>
                <li class="page-item" @click="getNextPage()">
                    <a class="page-link" href="#">
                        <i class="bi bi-chevron-right iten-navigation"></i>
                    </a>
                </li>
            </ul>
        </nav>
    </div>
</template>
  
<script>
export default {
    name: "Pagination",
    emits: ["update:pagedData"],
    props: {
        inputData: {
            type: Array,
            required: true
        },
        pagedData: {
            type: Array,
            required: true
        },
        elementsPerPage: {
            type: Number,
            required: false,
            default: 5
        }
    },
    data() {
        return {
            startPage: null,
            endPage: null,
            currentPage: 1
        }
    },
    mounted() {
        this.getDataPage(1);
    },
    computed: {
        totalPages() {
            return Math.ceil(this.inputData.length / this.elementsPerPage);
        }
    },
    methods: {
        getDataPage(numberPage) {
            this.currentPage = parseInt(numberPage);
            this.setPagedDate([]);

            this.startPage = (numberPage * this.elementsPerPage) - this.elementsPerPage;
            this.endPage = (numberPage * this.elementsPerPage);

            if (this.inputData) {
                this.setPagedDate(this.inputData.slice(this.startPage, this.endPage));
            }
        },
        getPreviousPage() {
            if (this.currentPage > 1) {
                this.currentPage--;
            }
            this.getDataPage(this.currentPage);
        },
        getNextPage() {
            if (this.currentPage < this.totalPages) {
                this.currentPage++;
            }
            this.getDataPage(this.currentPage);
        },
        setPagedDate(value) {
            this.$emit("update:pagedData", value);
        }
    },
    watch: {
        pagedData(value) {
            this.setPagedDate(value);
        },
        inputData(value) {
            this.setPagedDate(value);
        }
    }
}
</script>
  
<style scoped>
.container-pagination {
    display: flex;
    justify-content: center;
}

.page-link {
    background-color: #FFF;
    color: #15B115;
}

.page-link:hover {
    background-color: #15B115;
    color: #FFF;
}

.iten-navigation {
    font-size: 16px;
}

li {
    font-weight: 700;
}
</style>