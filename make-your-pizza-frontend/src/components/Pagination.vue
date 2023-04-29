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
    emits: ["update:paginatedList"],
    props: {
        receivedList: {
            type: Array,
            required: true
        },
        paginatedList: {
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
            return Math.ceil(this.receivedList.length / this.elementsPerPage);
        }
    },
    methods: {
        getDataPage(numberPage) {
            this.currentPage = parseInt(numberPage);
            this.setPaginatedList([]);

            this.startPage = (numberPage * this.elementsPerPage) - this.elementsPerPage;
            this.endPage = (numberPage * this.elementsPerPage);

            if (this.receivedList) {
                this.setPaginatedList(this.receivedList.slice(this.startPage, this.endPage));
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
        setPaginatedList(value) {
            this.$emit("update:paginatedList", value);
        }
    },
    watch: {
        paginatedList(value) {
            this.setPaginatedList(value);
        },
        receivedList(value) {
            this.setPaginatedList(value);
        }
    }
}
</script>
  
<style scoped>
@import '@/assets/css/colors.css';

.container-pagination {
    display: flex;
    justify-content: center;
}

.page-link {
    background-color: var(--var-system-color-white);
    color: var(--var-system-color-success);
}

.page-link:hover {
    background-color: var(--var-system-color-success);
    color: var(--var-system-color-white);
}

.iten-navigation {
    font-size: 16px;
}

li {
    font-weight: 700;
}
</style>