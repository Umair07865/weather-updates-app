<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <!-- <div class="d-flex align-center">
    
        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAQsAAAC8CAMAAABYM3sZAAABF1BMVEX///9Lz/983P8TtfD/wQb/0gUywvf/vgD/vQAAsu+A3v8As/AAr+//wgBIzv//0AAAtPcAs/p12v//78r/8tPa8vz/+u3//vj/9t9k1f//7cP/677/13b/2X3/33v/zQC55folvPQ6xvr/xR//02f/3Ir/4Zv/0Fzv+v5jyPT/5qz/yTj/zlP/35X/zEn/46P/2VDd8/ye2/fH6/uB0fWV2Pf/+OX/xiz/3Ib/5ZL/7bj/1Cf/213/1z3/6aX/6Zyr4Pj/2lceteG8yHIyuNvXzE1+v63EyWdnvb3kzjlJutNdvMWLwaOwxn54v7Hz0QDjzih4ubqivIzRvlrivziqvInswCa/vW2Vu5nZvk23vHuPuqqly7gqn/m9AAAPE0lEQVR4nN2da0PbOBaGMXFjG4VgQriES8EJlAAtLSRcSjvTDNvd7XZmp3Of2dn9/79jbSdOzpElWbYl2cw7X6atA/aTc5N0JC8t1VA7p3ao+6pvow46dyMUtrO6JfuB/dP7Xa23VJU2pihCDaSu33Ucx3bcwY7m+6pCFwkK2z2XuHw3Qefcar8107qdm4VtX2Zfvu3Mr77Qf3OGtbd4ONvOjhivF5e7XQO3Z1R7wC7c7Ij4cnG189rA7RnVFmDhnGRdDVxE4uonpzvgI5khYBeSe2Hi9oxqH37VWQHjAF78l4sXKHg6exkXLxJwKCO3Z1RbkMVBxrXQRY7N3J9Rwe/6TnzpOeQmU5k9Nd3DBxQXk8fylz5Nodwg/rJX5U3oaWobPKA4CHRz1SJPUpcAhnCs+gq4iLth6vaMCj6iIxqKQ2j2trH7M6muZMCABbj90tz9mdQ2DImn/OtQVfaXG5jNdCqXHvZlfekpC0xKiFjAUZzcfGCNtLO7JzV+2gEBg+8jKPfuK7tJI+oOXMdxVx8kLl1846LpnAHIqFmDuHopmbByJb7C+Vy4I5rBABW486Qy6mL46WYMPiO9nq2RDEQTGIvcKzVG3X5xfHxSizkOMOJyJZbEupeu69qvxBftz2A4AwmzeO3G6yh1qENg0Hdlxg5b3eyB54EbEnbcC4kVtpM5N4nfrVeofpKDIaOdk5d3BzIjkfuFP0m4qGYNbAQjw/pV6wCuNFQeZ1/aFcKAKGqwpgRnaOI7MjiDj1DYTvWjezgfF8MwNprax19D9XYRjrgqgkGhsB0zv1asFAwjM9c0CpPOKdDLCmCkrKIOxVakFAztrUXHdUWxtHRJwVjV/PtqjCIFQ26s3d14ePt8prdfb8hPYZ3QKAQzhhUIw8hc1dh5eP7ucI3S4dr7DzKJcaveKJaWLiAM8eBg93n05M8YioB89XXW4O2FU28UGIZg+vrhzSGbA+Dx7q0Qx75TcxQIhst5lp3nGSASHodvBHOGiEU9exK275J75EzZdkOTkACRWMcH3i+CPlJPFAsY7NnMjRwkZjjesofhIHbWFcVSNHJ0Hddhjdtv30g5B02DbRuv3PqjWIpqBmZWvM9pE3Maz5gj8VkFLjP3XjftFrCJOY33LEfZu3Ndd/AE25eeHxYmEcFYY5rG9k7lc3r5dfuuuFFMdfi86mdQpIcS/jE3ja+qfgol+lDKP+Ywnv0FuvnelzeKKYy1GsxmltMbRSgiGrWEMdwcjY4ijUabQ+GVClGEEbT6OX+gzaObsyZptVpeovD/g7PxZJN9vVIU9YExPBo3IwakQYsQEiIJxkcpE/lGLYp6uMnVTbPFoICJeK3m9RX81FvVKEIYsltbNWl4HbQ8IYe5vFZwM7eOB/Uonq29q5LE6CzLIrB5eK2zUfzBHQ0oQhjVjUuPglYOEDMcrWASflQHiWeHhtbk0poEkr5By2tM3mshYUtsVdOhUZDHOWjbePybahJrsw4giU3PijXst4qCmNJY//h3pSgO57N6pteQr/PHiTSNf2ggYdxLrooGCiw/+KcaEmuoQc7oesi1wD1IpHkJ7sV/5F+9/kkFCkTClttqdPuwv+q6F2VbqM94KEIIJOi3e71OZ3kl1PJyp9ez+kHD4/LwH/9VlsShnVJGK+f23sFq1AAbYSu1/j5sMJ+LhImy2etMEUBFf9Pp9cN/Zn/OL5dQDmmjiJ9Q8HVvnNzNOEwdqgSMETNSEC/o92gKmEinzQkypUIoi4TN3XzSfXXpunRbTOHB7YTlH4T0OyIQcxz9BstZ1r8tbBRsEmzD2DhNcYgNo+gSCitqkoa1nAkiwdFjFWj+Z7UkbNahEacu59KCe30ZKEIS2SYBcfQYruI/fslNYo3jHjPDoHt46F7ChYr1zKdRENKWtQlAIx1FSW4YIqNgWP4ezyqEGx75SscKr9nJSyKmYaVokI8qSdipDUfH/AuLDGxHNArS6BUhEcHoBDQMPwcMsXvMHhFHT8EnCqC4ot2cBIWMIjENOqP40tlEgkSq2YB7mcTxVWml/MMqTmJqGtQPXP9OkXvMnhI5yQXzEldmC1xaTfw1FvePhWg/Wf+3BAkpo4gfFNVQr+k04jjuxUmxMuvGo1CU8I+5afQpt/MzxybSJFIdpPCTIYfB/W7RjoTNFo2iNIkIRpsinBE/Zd1jKlxD3dpOwmF1f6/MDAf27TBqqkARRVAMw/9eiXvMvn38wNthCR4W4cfnJRfkx+iWFVlFDIOyjHXu5I5MHsVKbSPa6uboKOeJ8hB1KKKYgQIoeVTiHlO70LJ9CXuIVz6DQBg4QfnMxFqAhKb9qEfIjkvWFWnh1MrIJfndYyodZ5ziwUNTMYrlDo7LqfKzIAlbxzl91zi8KSYRjVsRayp8FnKPqTScB4E9pKecBRU/kyLjyw8//PDly6q9Wtgu1B9Oh82ir9pDYiHD8z99+vy4nujx848//WwX4qH+XE8cLXSQWF7GXoJWVMI/+L7/+Y9f8uNQvk8ZJRG16TRR+DObGSuSxF//+Gteb3FUb/yEtQUJlKNYWe70LMtqi1FMcfjf/5aLRubhsDmFSk7VgXNluWe12yEJeiqDh2P9xzw0HJmTm3JoDF1XsVlMQYQkRCuuNI3v5WGotgt4I2rNIiRh5SQRyW/8LktD8XkXcMVQqVkUJBFp/VtJGIrzCHIRZQORlRkJq5+fRGQaj3IJVnF9gYoLRSSWl2ck2qmFAUkRX8pP1B7hCNcBiKKSc6VjTZVVU4i0/ofMEonS8Qisv4miyNmbGoUlMor4n6YdPZyr1v+bDUPpuRLDPvz1alBkRQoS/hcEzX6/3263+/1mELBx+N9lwlA2fzEcjQNYZxEl8xYZ/hECCvozu1mo32S1bWS6iap5raOoyxsPmFS4SIKCWWeGv66Z4jATK/dmBVAl851Ru3vqTj0FE76d5MGYKII+BwQv6fj/EbMon1KvG8w21kABilkqZYUK0uCZxIJG+jMDIYuyaeSGtTOooSRczFCwxqSkIbSJRHSUIZ9FXlLyPQPX3E0x5YvOzvyRaBiESJGwouyDP+kL4ifzMAVpjRr8zubyoZNr7STIdA/wSUxDEDJS4eLh4PTghWQpeiZqdy8dOnnfr6R7cGCQj3zDwE/XXXWdeGH5YC8zjowyNoOUI7HSw9/93PNJkIeElXIw/0+eWeC+HHBcsuNeis1jLNwNQsqO13u0GyRpNZdRMGCQgGMY1GQn9Y+uze87oLtCAAVCvEazXy5cdNIRYQpDPlIshAOo/5OMi6RbGkPzuDthmMeQM04icZt3bznV755XrEcKK8mgAAmLTq1sw6AK8ANmp6vjXtDLSezO/7Aiivv+y1HgorCsRrMYCmqI6//Kekyq73ef1/VLzX0N2a7RFPb951EqWJQWutVH1jNSG/DuuR3Q2JfSDhK6hnS7e7YYwaKsmihi/M74uqllog1uCzQawaWHz16gzCQiKSdhUYbBmAtO9bvfMTCkLGicaudV0LkJRFcWaoRyif9byixSKyNbXBaL2S+6yZuom+2eSoOHREJOkkqrjBmtrTvWRhpkQpRVlOrxZkoLidAw4E3Tw1X2tqnu/QBuNJtpkXzPcLDwlDcgaUJBRQzsJPztdFvnxw5lHvPDMykPUd6WpiGdJoLZjyoxxPuWuy8ugXksXomC06l6FJqCRaQ2XNH7BJ0k+1j67d3Z/lRn8aYHqlmxrby7QhsJCztJkBE4Gbo937+4OFlYEKq91Uz6Q+lJp4lgXeT/IushPE2gWWjoudHoIRbOJGAWo+BLvtDUvIo5f0o6SeB5DDJfUSy48xa1HxHlwWJFLwq04DQvw4WvRRNojJKIcg/RGixiFuD+k0kMmXd8sYQCp/J2Xr3BIhIarA5KxE3KRdQHTt0kqDI8TiSFm0/gbjrVA7KoC0m7YLXl/1wGxRIyMbUkDASLSDCp/l6qJQm4iPIyS3+woFn8aQvfJikWDBfKI6cJEhSLuxKr6nAsorrOMoMCsmj9rzgJaluIUhfROwxhs/Cuy7AAlZbacGEMhToWZ+AnKd0sZAyFOhZgyKu0ujCTQlIsJqpYKEwjBlEIWWy8OpEfvMNRnjoWnewn0MPiCD3cazd6C7otu2dCCwujKBCLEXy25KV3sufd6mBhFgUcj3jwMPbz+eKpK7fLSkO8MIsCjVM9eA476PqUgwF+kqI8YhgFnr8AT7aD3rEsE0FhfaFifm/FZAaJBea1SACeDPcXyMBQXHeaqzbnAl8mOQNP1qXespy9YxdM5ahYDjCPAoVOVHbmfm8tXBwhpVlYxlHg0IlS6kleGCN1Y/YV01EzFpwGJ/h1HoOcR7cO4VxOqURSQaiwqJbXJn62bXovRRaMBgzDJVh0KvAPC2dU74Z6trwwYBsKeWJGYeFl9lbqFUBpGMIzUiYK9luuVGQUuHkNVRcJDIqF+I0LKGAUdJKqjALv3ku5SAyD7uESGgYMxIUyiYH1IJ5QT6N3xXo8CoY4YqCFs/ylZ68q94gEowWdRRJt4RcuCIuMK3TkSU7DqJQE3t+KCy0ejNQh2VgwLeWLGNWSwB7CipwJDMAiY3N7sSOSVjoVk0AjEfG07wJG5nAVeZ3k+nJlWXSBAt823yxiGNNy3M3coInWziTCZ/UmEQnv/GkdCR9x+zg6zXVVYhID728UT+nUAwSNgpdEgHa6Us0IE+rcQR6M+ESwOoBIbdZtMWuLQsI/mQOjMzsIqwZCh5M0OCVnQVHN8YSCMT0hriYcLMa5MsLAmVf0pokERkgheu9SXewhFm0UrAFqKVGbabz2SgQholAnDBbzMJCMHJJbR/Qmq0a7Rk4xF+uQmFapRgOW6M13pPgeWm1iHlXXGqtGwdqfWmDHvU4xj1FqtM6yHy23mFu4uScamVafc7anDquIYDAOAYlPuqqaQzsCwT52oKWwsEDaZJ6IEp+A1qxQ8R1wrGKiCQUPRsXi35LXUFd5p3VVQxY8ES1RE2goOEOpXvIaR3pRLAneilorEU35g5Lobbk1UegeOiMF0LBZbxohCbVjMaEmNY4anlESka5JPWl43niYffeqNQm4BxRWJa/VPzIPItbVmNQHB/FawXUFJrHQ5k1oHRkn9BmQ1/LOJoYyh0jDzetxelbNpIKzayPR8v8Wj+akdAQ5hQAAAABJRU5ErkJggg=="
          width="100"
          rounded
        />
     
      </div> -->
      <v-icon style="font-size:3rem" class="ml-4">mdi-clouds</v-icon>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Weather Hub</span>
        <v-icon>mdi-clouds</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main  >
       <GridSyetem/>
    </v-main>
  </v-app>
</template>

<script>

import GridSyetem from './components/GridSystem.vue'
export default {
  name: 'App',

  components: {
    GridSyetem
  },

  data: () => ({
    //
  }),
};
</script>
