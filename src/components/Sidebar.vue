<template>
    <div class="sidebar" id="sidebar">
        <ul class="sidebar-menu" v-for="item in sideBarLists" :key="item.id">
            <li class="sidebar-item">
                <router-link
                    class="link-redirect"
                    :to="{
                        name: 'Collection',
                        params: { collectionName: item.collectionName },
                    }"
                >
                    <p class="collection-name">
                        {{ item.name }}
                    </p>
                </router-link>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "SideBar",
    data() {
        return {
            sideBarLists: [
                { name: "BEST SELLER", collectionName: "best-seller", id: 1 },
                {
                    name: "BASIC LINE",
                    collectionName: "basic-collection",
                    id: 3,
                },
                {
                    name: "TẤT CẢ SẢN PHẨM",
                    collectionName: "all-products",
                    id: 2,
                },
                { name: "ÁO THUN", collectionName: "tshirt", id: 1 },
                { name: "ÁO SƠMI", collectionName: "shirt", id: 4 },
                { name: "ÁO KHOÁC", collectionName: "outerwear", id: 7 },
                { name: "QUẦN", collectionName: "pants", id: 5 },
                { name: "PHỤ KIỆN", collectionName: "accessories", id: 6 },
                {
                    name: "OUTLET SALE",
                    collectionName: "sale-end-season",
                    id: 8,
                },
            ],
            collection: {
                id: 1,
                name: "",
                path: "",
                products: [],
            },
        };
    },
};
</script>

<style lang="scss" scoped>
#sidebar.sidebar {
    height: 100%;
    width: 100%;
    position: relative;
    left: 0;
    top: 0;
    padding: 30px;
    background-color: var(--primary-color);
    .sidebar-item {
        text-decoration: none;
        list-style-type: none;
        list-style-position: outside;
        padding-bottom: 15px;
        .link-redirect {
            color: black;
            text-decoration: none;
            text-transform: uppercase;
            font-size: 18px;
            font-weight: 700;
            line-height: 27px;
        }
    }
}
</style>
