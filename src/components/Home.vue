<template>
	<v-container>
		<v-layout row wrap class="mb-2">
			<v-flex xs12 sm6 class="text-xs-center text-sm-right">
				<v-btn large to="/meetups" class="info">Explore Meetups</v-btn>
			</v-flex>
			<v-flex xs12 sm6 class="text-xs-center text-sm-left">
				<v-btn large to="/meetup/new" class="info">Organize Meetup</v-btn>
			</v-flex>
		</v-layout>
		<v-layout row wrap class="mt-2">
			<v-flex xs12>
				<v-carousel style="cursor: pointer;">
					<v-carousel-item v-for="meetup in meetups" :key="meetup.id" :src="meetup.imageUrl" @click="onLoadMeetup(meetup.id)">
						<div class="title">{{ meetup.title }}</div>
					</v-carousel-item>
				</v-carousel>
			</v-flex>
		</v-layout>
		<v-layout row wrap class="mt-2">
			<v-flex xs12 class="text-xs-center">
				<p>Join our awesome meet ups!</p>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
	/* eslint-disable */
	export default {
		data () {
			return {
				meetups: [
					{ imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ad/Seattle_waterfront_pano.jpg/800px-Seattle_waterfront_pano.jpg', id: 'asdasdfeasdf', title: 'Meetup in Seattle' },
					{ imageUrl: 'http://zoneone.wf7woxluljv.maxcdn-edge.com/blog/wp-content/uploads/2013/04/westseattleaerialntos-e1366997241462.jpg', id: 'iv2123skvadf', title: 'Meetup in West Seattle' }
				]
			}
		},
		methods: {
			onLoadMeetup (id) {
				this.$router.push('/meetups/' + id);
			}
		}
	}
</script>

<style scoped>
	.title {
		position: absolute;
		bottom: 50px;
		background-color: rgba(0, 0, 0, 0.5);
		color: white;
		font-size: 2em;
		padding: 20px;
	}
</style>
