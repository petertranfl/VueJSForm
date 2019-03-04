<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Sign Up!</h1>
                    <hr>
                    <app-full-name v-model="userData.fullName"></app-full-name>
                     <div class="form-group">
                        <label for="email">Email</label>
                        <input
                            type="text"
                            id="email"
                            class="form-control"
                            v-model="userData.email"
                        >
                    </div>
                     <div class="form-group">
                        <label for="password">Password</label>
                        <input
                            type="text"
                            id="password"
                            class="form-control"
                            v-model="userData.password"
                        >
                    </div>
                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                            <p> Store Data? </p>
                            <label for="YesStoreData">
                                <input
                                        type="radio"
                                        id="YesStoreData"
                                        value="Yes"
                                        v-model="storeData"> Yes
                            </label>
                            <label for="NoStoreData">
                                <input
                                        type="radio"
                                        id="NoStoreData"
                                        value="No"
                                        v-model="storeData"> No
                            </label>
                        </div>
                    </div>
                    <button type="button" class="btn btn-primary" @click.prevent="isSubmitted = true">Submit</button>
                </div>
            </div>
        </form>
        <hr>
        <data-summary :userData="userData" :storeData="storeData" v-if="isSubmitted"></data-summary>
    </div>
</template>

<script>
    import DataSummary from './DataSummary.vue'
    import FullName from './FullName.vue'

    export default {
        data () {
                return {
                    userData: {
                        fullName: 'Peter Tran',
                        email: '',
                        password: '',
                    },
                    storeData: '',
                    isSubmitted: false,
                }
            },
        components: {
            dataSummary: DataSummary,
            appFullName: FullName
        }
    }
</script>

<style>
</style>
