<template>
    <div class="container">
        <form  v-if="formSubmitted == false">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
					<h1>Input Forms</h1>
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
					<!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

					<!-- Exercise 3 -->
					<!-- Edit the Example from above and create a custom "Full Name" Control -->
					<!-- which still holds the First Name and Last Name Input Field -->

					<app-name-holder v-model="userId.fullName"></app-name-holder>

					<!-- Mail -->
					<div class="form-group">
						<label for="email">Your Mail</label>
						<input
							type="text"
							id="email"
							class="form-control"
							v-model.lazy="userId.email">
					</div>
                    <!-- Password -->
					<div class="form-group">
						<label for="password">Your Password</label>
						<input
							type="password"
							id="password"
							class="form-control"
							v-model.lazy="userId.password">
					</div>
					<div class="form-group">
						<h3>Store data?</h3>
							<label>
								<input
									type="radio"
									id="store-data-yes"
									value="Yes"
									v-model="userId.storeData"> Yes
							</label>

							<label>
								<input
									type="radio"
									id="store-data-no"

									value="No"
									v-model="userId.storeData"> No
							</label>
					</div>
                </div>
				<!-- Store Data? Yes/No -->


				<!-- Exercise 2 -->
				<!-- Only display the Form if it has NOT been submitted -->
				<!-- Display the Data Summary ONCE the Form HAS been submitted -->
				<div class="row">
					<div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
						<button
							class="btn btn-primary"
							@click.prevent="formSubmitted = true">Submit Form
						</button>
					</div>
				</div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="formSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userId.fullName }}</p>
                        <p>Mail: {{ userId.email }}</p>
                        <p>Password: {{ userId.password }}</p>
                        <p>Store in Database?: {{ userId.storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
	import NameHolder from './components/NameHolder.vue';
    export default {
		data() {
			return {
				userId: {
					fullName: 'Tamer Yagli',
					firstName: '',
					lastName: '',
					email: '',
					password: '',
					storeData: 'No'
				},
				formSubmitted: false
			};
		},
		components: {
			'app-name-holder': NameHolder
		}
    }
</script>

<style>
</style>
