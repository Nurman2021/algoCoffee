  <script>
	  // import Swiper core and required modules
	  import { Navigation, Pagination, A11y } from 'swiper';

	  import { Swiper, SwiperSlide } from 'swiper/svelte';

	  // Import Swiper styles
	  import 'swiper/css';
	  import 'swiper/css/navigation';
	  import 'swiper/css/pagination';
  </script>
  	<Swiper
    modules={[Navigation, Pagination, A11y]}
    spaceBetween={50}
    slidesPerView={3}
    navigation
    pagination={{ clickable: true }}
    breakpoints={{
                            320: {
                                slidesPerView: 1,
                                spaceBetween: 20,
                            },
                            768: {
                                slidesPerView: 2,
                                spaceBetween: 40,
                            },

                        }}

   
  >
    <SwiperSlide>
    	<img src="/images/galery-1.jpg"/>
    </SwiperSlide>
   <SwiperSlide>
    	<img src="/images/galery-2.jpg"/>
    </SwiperSlide>
    <SwiperSlide>
    	<img src="/images/galery-3.jpg"/>
    </SwiperSlide>
    <SwiperSlide>
    	<img src="/images/galery-4.jpg"/>
    </SwiperSlide>

  </Swiper>

 