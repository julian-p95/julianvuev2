<template>
<div class="w-full mb-6 md:mb-0">
    <div class="project-details-container">
        <div class="usage-filter count-box">
            {{ items.length }}
        </div>
        
    </div>
    <div class="relative filter-section  mb-4">
        <div class="usage-filter">
            <input @keyup="searchEngine(searchValue)" v-model="searchValue" placeholder="Search Engine" class="
          block
          appearance-none
          bg-gray-200
          border border-gray-200
          text-gray-700
          py-3
          px-4
          pr-8
          rounded
          leading-tight
          focus:outline-none focus:bg-white focus:border-gray-500
        " id="grid-state" />
        </div>
       
        
        <div class="
          pointer-events-none
          absolute
          inset-y-0
          right-0
          flex
          items-center
          px-2
          text-gray-700
        ">
            <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                <path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z" />
            </svg>
        </div>
        <button @click="resetData()" class="bg-gray-200 reset-btn  text-dark font-bold py-2 px-4">
            Reset
        </button>
    </div>
</div>

<EasyDataTable ref="data-table" table-class-name="data-table" class="font-mono" :headers="headers" :items="items" :loading="loading" :header-item-class-name="getHeaderClassNameByIndex" :body-item-class-name="getItemClassNameByIndex" updatePage @click-row="expandRow" theme-color="#FFC40C" header-text-direction="center" body-text-direction="center" alternating>
    <template #item-link="{ link }">
        <a class="repo-link after:content-['_↗'] after:text-sm after:pb-2" :href="link" target="_blank" rel="noopener noreferrer">{{ link }}</a>
    </template>
    <template #expand="item">
        <div class="expended-row">
            <div class="details">
                <h2 class="font-bold">Details</h2>
                <p v-if="!item.details">None 😢</p>
                <p v-else>{{ item.details }}</p>
            </div>
            <div class="description">
                <h2 class="font-bold">Description</h2>
                <p v-if="!item.description">None 😢</p>
                <p v-else>{{ item.description }}</p>
            </div>
        </div>
    </template>
</EasyDataTable>
</template>

<style> 





 

.usage-filter.count-box {
    background: white;
    padding: 0px 3px;
    border-radius: 10px;
    margin-right: 225px;
    margin-top: -600px;
    margin-bottom: 13px;
    font-size: 15px;
}
.sortable.none .sortType-icon {
    display: none !important;
}

.previous-page__click-button.first-page .arrow,
.next-page__click-button.last-page .arrow {
    border-color: black !important;
}

.easy-data-table__rows-selector ul.select-items li.selected {
    color: black !important;
}

.previous-page__click-button .arrow,
.next-page__click-button .arrow {
    border-color: white !important;
}

.data-table {
    --easy-table-border: 6px solid #445269;
    --easy-table-row-border: 3px solid #445269;

    --easy-table-header-font-size: 14px;
    --easy-table-header-height: 10px;
    --easy-table-header-font-color: #ffffff;
    --easy-table-header-background-color: #0c173c;

    --easy-table-header-item-padding: 3px 15px;

    --easy-table-body-even-row-font-color: #ffffff;
    --easy-table-body-even-row-background-color: #0f234b;

    --easy-table-body-row-font-color: #ffffff;
    --easy-table-body-row-background-color: #0f234b;

    --easy-table-body-row-height: 0px;
    --easy-table-body-row-font-size: 18px;

    --easy-table-body-row-hover-font-color: #0c173c;
    --easy-table-body-row-hover-background-color: #eee;

    --easy-table-body-item-padding: 3px 10px;

    --easy-table-footer-background-color: #0c173c;
    --easy-table-footer-font-color: #c0c7d2;
    --easy-table-footer-font-size: 14px;
    --easy-table-footer-padding: 0px 10px;
    --easy-table-footer-height: 50px;

    --easy-table-rows-per-page-selector-width: 70px;
    --easy-table-rows-per-page-selector-option-padding: 10px;

    --easy-table-scrollbar-track-color: #0c173c;
    --easy-table-scrollbar-color: #0c173c;
    --easy-table-scrollbar-thumb-color: #4c5d7a;
    --easy-table-scrollbar-corner-color: #0c173c;

    --easy-table-loading-mask-background-color: #0c173c;
}
.reset-btn {
    background: white;
    border-radius: 4px;
}
.relative.filter-section {
    width: 100%;
    display: flex;
    justify-content: space-around;
}

.usage-filter {
    display: flex;
    justify-content: center;
    margin-top: 0x;
    margin-bottom: 0px;
}

.usage-filter .filter-label {
    color: wheat;
    margin-top: 10px;
    margin-right: 30px;
    vertical-align: middle;
}

select#grid-state {
    padding: 7px;
    margin-top: 0px;
    
    
}

thead.vue3-easy-data-table__header tr th:nth-child(2)>span {
    justify-content: left !important;
}

thead.vue3-easy-data-table__header tr th:nth-child(3)>span {
    justify-content: left !important;
}

thead.vue3-easy-data-table__header tr th:nth-child(4)>span {
    justify-content: left !important;
}

thead.vue3-easy-data-table__header tr th:nth-child(5)>span {
    justify-content: left !important;
}
thead.vue3-easy-data-table__header tr th:nth-child(6)>span {
    justify-content: left !important;
}

.expended-row {
    display: flex;
    justify-content: start;
    text-align: left;
}


.expended-row .details {
    margin-right: 50px;
    margin-left: 10px;
}

.vue3-easy-data-table__body td .expand-icon {
    border-width: 0 6px 6px 0 !important;
    padding: 5px !important;
}

tbody.vue3-easy-data-table__body.row-alternation tr td {
    white-space: nowrap;
}

tbody.vue3-easy-data-table__body.row-alternation tr td:nth-child(2) {
    text-align: left;
}

tbody.vue3-easy-data-table__body.row-alternation tr td:nth-child(3) {
    text-align: left;
}


tbody.vue3-easy-data-table__body.row-alternation tr td:nth-child(4) {
    text-align: left;
}


tbody.vue3-easy-data-table__body.row-alternation tr td:nth-child(5) {
    text-align: left;
}


tbody.vue3-easy-data-table__body.row-alternation tr td:nth-child(6) {
    text-align: left;
}



</style>

<script lang="ts">
import {
    defineComponent
} from "vue";
import Vue3EasyDataTable, {
    Header
} from "vue3-easy-data-table";
import type {
    ClickRowArgument
} from "vue3-easy-data-table";
import "vue3-easy-data-table/dist/style.css";

const HEADER_REACTIVE_CLASSES: any = {
    expand: "!px-0 sm:px-0",
    rank: "!pl-2 !pr-0 sm:!px-3 text-0 before:content-['#'] before:inline before:text-lg sm:text-base sm:before:content-none",
    name: "text-lg sm:text-xl",
    updatedAt: "hidden md:table-cell",
    createdAt: "hidden lg:table-cell",
    stargazers: "text-0 before:content-['★'] before:inline before:text-2xl sm:text-base sm:before:content-none",
    loc: "text-0 before:content-['LoC'] before:inline before:text-lg sm:text-base sm:before:content-none",
    score: "text-lg sm:text-xl",
    all: "break-words sm:text-lg lg:text-xl text-black",
};

const REACTIVE_CLASSES: any = {
    expand: "expand-button !px-0 sm:!px-3",
    rank: "repo-rank !pl-2 !pr-0 sm:!px-3",
    name: "break-all text-ellipsis",
    updatedAt: "hidden md:table-cell",
    createdAt: "hidden lg:table-cell",
    all: "text-sm sm:text-lg",
};

export default defineComponent({
    props: {
        tool: {
            type: String,
            required: true,
        },
    },
    components: {
        EasyDataTable: Vue3EasyDataTable,
    },
    data() {
        return {
            headers: [{
                text: "",
                value: "",
                sortable: true,
            }, ],
            colms: [],
            rows: [],
            items: [{
                context: '',
                project: '',
                classification: '',

            }],
            mainData: [{
                context: '',
                project: '',
                classification: ''
            }],
            subCat: "",
            searchValue: "",
            loading: true,
            resetOption:false
        };
    },
    methods: {
        resetData(){
            location.reload();
        },
        filterData(subCat: String) {
            this.items = this.mainData;
            if (subCat != "")
                this.items = this.items.filter((item) => item.context == subCat);
        },
        searchEngine(searchValue: string) {
            this.items = this.mainData;
            if (searchValue != "")
                this.items = this.items.filter((item) => {
                    if(item.project.toLowerCase().search(searchValue.toLowerCase())!=-1 || item.classification.toLowerCase().search(searchValue.toLowerCase())!=-1)
                    {
                        return item;
                    }
                });
        },
        async fetchData() {
            this.loading = true;
            this.mainData = [];

            var self = this;
            let url = "https://docs.google.com/spreadsheets/d/";
            let sheet_id = "1s4Die_W5Euxq2Hi1rznWMQm5GKZ9v7EjjdzXOpiCS2A";
            let query1 = "/gviz/tq";
            let endpoint = `${url}${sheet_id}${query1}`;
            await fetch(endpoint)
                .then((res) => res.text())
                .then((data) => {
                    const temp = data.substring(47).slice(0, -2);
                    const json = JSON.parse(temp);
                    self.colms = json.table.rows[0].c.map((col: {
                        v: String
                    }) => {
                        if (col && col.v != null && col.v !== undefined) {
                            return col.v.trim().toLowerCase();
                        }
                    });

                    json.table.rows.forEach((row: {
                        c: any[];
                    }, index: Number) => {
                        if (index != 0) {
                            var obj: any = {
                                project: "",
                                tool: "",
                                context: "",
                                description: "",
                                classification: "",
                                link: "",
                                details: "",
                            };

                            row.c.map((value: {
                                v: String
                            }, key: any) => {
                                if(this.resetOption==true)
                                obj[self.colms[key]] = value.v;
                                else if (self.colms[key] == 'tool' || self.colms[key] == 'context')
                                    obj[self.colms[key]] = value.v.toLowerCase().trim();
                                else
                                    obj[self.colms[key]] = value.v;
                            });

                            if (self.tool == '') self.mainData.push(obj);
                            else if (self.tool != '' && obj.tool.trim() == self.tool) self.mainData.push(obj);

                        }
                    });
                });
            this.resetOption = false;
            this.items = self.mainData;
            this.loading = false;
        },
        expandRow(item: ClickRowArgument) {
            let xpath = `//tr[td[text()='${item["rank"]}'][contains(@class, 'repo-rank')]]/td[contains(@class, 'expand-button')]`;
            let expandButton = document.evaluate(
                xpath,
                document,
                null,
                XPathResult.FIRST_ORDERED_NODE_TYPE,
                null
            ).singleNodeValue as HTMLElement;
            expandButton.click();
        },
        async shrinkAllRows() {
            let expandButtons = document.querySelectorAll(
                ".expanding"
            ) as NodeListOf < HTMLElement > ;
            expandButtons.forEach((button) => {
                button.click();
            });
        },
        getHeaderClassNameByIndex(header: Header, index: string) {
            return (
                HEADER_REACTIVE_CLASSES.all +
                " " +
                HEADER_REACTIVE_CLASSES[header.value]
            );
        },
        getItemClassNameByIndex(column: string, rowNumber: number) {
            return REACTIVE_CLASSES.all + " " + REACTIVE_CLASSES[column];
        },
        getFlagEmoji(countryCode: string) {
            if (countryCode == undefined) return;
            if (countryCode == "ZH") countryCode = "CN";
            if (countryCode == "JA") countryCode = "JP";
            const codePoints = countryCode
                .toUpperCase()
                .split("")
                .map((char) => 127397 + char.charCodeAt(0));
            return (
                String.fromCodePoint(codePoints[0]) +
                String.fromCodePoint(codePoints[1])
            );
        },
    },
    mounted() {
        this.headers = [{
                text: "Project",
                value: "project",
                sortable: true,
            },
            {
                text: "Classification",
                value: "classification",
                sortable: true,
            },
            {
                text: "Context",
                value: "context",
                sortable: true,
            },
            {
                text: "Tool",
                value: "tool",
                sortable: true,
            },
            {
                text: "Links",
                value: "link",
                sortable: true,
            }
        ];
        this.fetchData();
    },
    watch: {
        tool() {
            this.subCat = "";
            this.shrinkAllRows();
            this.fetchData();
            (this.$refs["data-table"] as any).updatePage(1);
        },
    },
    updated() {
        Array.from(document.getElementsByClassName("repo-link")).forEach(function (
            el
        ) {
            el.addEventListener("click", (e) => {
                e.stopPropagation();
            });
        });
    },
});
</script>
