<template>
        <section>
            <div class="block">
                <b-field grouped group-multiline>
                    <div class="control">
                        <b-switch v-model="reduce">Reduced</b-switch>
                    </div>
                    <div class="control">
                        <b-switch v-model="expandOnHover">Expand on hover</b-switch>
                    </div>
                    <div class="control">
                        <b-field label="Mobile Layout" label-position="on-border">
                            <b-select v-model="mobile">
                                <option :value="null"></option>
                                <option value="reduce">Reduced</option>
                                <option value="hide">Hidden</option>
                                <option value="fullwidth">Fullwidth</option>
                            </b-select>
                        </b-field>
                    </div>
                </b-field>
            </div>
            <b-sidebar
                    position="static"
                    :mobile="mobile"
                    :expand-on-hover="expandOnHover"
                    :reduce="reduce"
                    type="is-light"
                    open
            >
                <div class="p-1">
                    <div class="block">
                        <img
                                src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
                                alt="Lightweight UI components for Vue.js based on Bulma"
                        />
                    </div>
                    <b-menu class="is-custom-mobile">
                        <b-menu-list label="Menu">
                            <b-menu-item icon="information-outline" label="Info"></b-menu-item>
                            <b-menu-item active expanded icon="settings" label="Administrator">
                                <b-menu-item icon="account" label="Users"></b-menu-item>
                                <b-menu-item icon="cellphone-link" label="Devices"></b-menu-item>
                                <b-menu-item icon="cash-multiple" label="Payments" disabled></b-menu-item>
                            </b-menu-item>
                            <b-menu-item icon="account" label="My Account">
                                <b-menu-item icon="account-box" label="Account data"></b-menu-item>
                                <b-menu-item icon="home-account" label="Addresses"></b-menu-item>
                            </b-menu-item>
                        </b-menu-list>
                        <b-menu-list>
                            <b-menu-item label="Expo" icon="link" tag="router-link" target="_blank" to="/expo"></b-menu-item>
                        </b-menu-list>
                        <b-menu-list label="Actions">
                            <b-menu-item icon="logout" label="Logout"></b-menu-item>
                        </b-menu-list>
                    </b-menu>
                </div>
            </b-sidebar>
        </section>
</template>

<script>
    export default {
        name: "ItemComponent",
        data() {
            return {
                expandOnHover: false,
                mobile: "reduce",
                reduce: false
            };
        }
    }
</script>

<style scoped>
    .p-1 {
        padding: 1em;
    }
    @media screen and (max-width: 1023px) {
        .b-sidebar {
            .sidebar-content {
                &.is-mini-mobile {
                    &:not(.is-mini-expand),
                    &.is-mini-expand:not(:hover) {
                        .menu-list {
                            li {
                                a {
                                    span:nth-child(2) {
                                        display: none;
                                    }
                                }
                                ul {
                                    padding-left: 0;
                                    li {
                                        a {
                                            display: inline-block;
                                        }
                                    }
                                }
                            }
                        }
                        .menu-label:not(:last-child) {
                            margin-bottom: 0;
                        }
                    }
                }
            }
        }
    }
    @media screen and (min-width: 1024px) {
        .b-sidebar {
            .sidebar-content {
                &.is-mini {
                    &:not(.is-mini-expand),
                    &.is-mini-expand:not(:hover) {
                        .menu-list {
                            li {
                                a {
                                    span:nth-child(2) {
                                        display: none;
                                    }
                                }
                                ul {
                                    padding-left: 0;
                                    li {
                                        a {
                                            display: inline-block;
                                        }
                                    }
                                }
                            }
                        }
                        .menu-label:not(:last-child) {
                            margin-bottom: 0;
                        }
                    }
                }
            }
        }
    }
</style>