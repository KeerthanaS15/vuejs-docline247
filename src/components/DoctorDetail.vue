<template>
    <div>
        <div class="p-doctor__info m-doctor-card" v-for=" doctorDetail of doctorDetails" :key="doctorDetail.id">
            <img src="../assets/images/Dr.Smith.svg" alt="doctor" class="m-doctor-card__img">

            <div class="m-doctor-card__info m-doctor-card-side">
                <span class="m-doctor-card-side__list m-doctor-card-side__list--name">Dr. {{doctorDetail.name}}</span>
                <span class="m-doctor-card-side__list">{{doctorDetail.category}}</span>
                <span class="m-doctor-card-side__list">{{doctorDetail.gender}} - {{doctorDetail.age}}yrs</span>
                <span class="m-doctor-card-side__list">{{doctorDetail.year_of_employment}} - Present</span>

                <button class="m-btn m-btn--blue m-doctor-card-side__list--btn">BOOK AN APPOINTMENT</button>
            </div>
        </div> 
    </div>
</template>

<script>
import axios from "axios";
export default {
  data () {
    return {
        doctorDetails:[]
    }
  },
async mounted() {
    try {
      const res = await axios.get(`http://localhost:3001/doctorDetails`);
      this.doctorDetails = res.data;
    } catch (error) {
      console.log(error);
    }
  }
}
</script>

<style lang='scss' scoped>
.m-doctor-card{
    background-color: #F2F2F2;
    height: 186px;
    border-radius: 15px;
    display: flex;
    justify-content: space-evenly;
    padding: 16px;
    align-items: center;
    column-gap: 5%;
}
.m-doctor-card-side{
    display: flex;
    flex-flow: column;

    &__list{
        &--btn{
            font-size: 12px;
            width: 170px;
            height: 33px;
            font-weight: bold;
            margin-top: 5%;
        }
        &--name{
            font-weight: bold;
            font-size: 18px;
        }
    }
}
.m-btn {
	display: flex;
	align-items: center;
	justify-content: center;
	text-align: center;
	height: 56px;
	border-radius: 16px;
	border: none;
	font-size: 18px;
	font-weight: 500;

	&--white {
		color: #237d9e;
		background-color: #fff;
	}

	&--blue {
		color: #fff;
		background-color: #237d9e;
		border: 0.5px solid #fff;
	}
}
.p-doctor{

    &__info{
        margin: 0 28px 28px 28px;
    }
}
</style>
