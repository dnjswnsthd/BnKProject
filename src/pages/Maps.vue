<template>
  <card type="plain" title="Google Maps">
    <div id="map" class="map"></div>
  </card>
</template>
<script>
export default {
  mounted() {
    let myLatlng = new window.google.maps.LatLng(
      35.14570387700273,
      129.06613268630375
    );
    let mapOptions = {
      zoom: 15,
      center: myLatlng,
      scrollwheel: false, //we disable de scroll over the map, it is a really annoing when you scroll through page
      styles: [
        {
          elementType: "geometry",
          stylers: [
            {
              color: "#1d2c4d",
            },
          ],
        },
        {
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#8ec3b9",
            },
          ],
        },
        {
          elementType: "labels.text.stroke",
          stylers: [
            {
              color: "#1a3646",
            },
          ],
        },
        {
          featureType: "administrative.country",
          elementType: "geometry.stroke",
          stylers: [
            {
              color: "#4b6878",
            },
          ],
        },
        {
          featureType: "administrative.land_parcel",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#64779e",
            },
          ],
        },
        {
          featureType: "administrative.province",
          elementType: "geometry.stroke",
          stylers: [
            {
              color: "#4b6878",
            },
          ],
        },
        {
          featureType: "landscape.man_made",
          elementType: "geometry.stroke",
          stylers: [
            {
              color: "#334e87",
            },
          ],
        },
        {
          featureType: "landscape.natural",
          elementType: "geometry",
          stylers: [
            {
              color: "#023e58",
            },
          ],
        },
        {
          featureType: "poi",
          elementType: "geometry",
          stylers: [
            {
              color: "#283d6a",
            },
          ],
        },
        {
          featureType: "poi",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#6f9ba5",
            },
          ],
        },
        {
          featureType: "poi",
          elementType: "labels.text.stroke",
          stylers: [
            {
              color: "#1d2c4d",
            },
          ],
        },
        {
          featureType: "poi.park",
          elementType: "geometry.fill",
          stylers: [
            {
              color: "#023e58",
            },
          ],
        },
        {
          featureType: "poi.park",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#3C7680",
            },
          ],
        },
        {
          featureType: "road",
          elementType: "geometry",
          stylers: [
            {
              color: "#304a7d",
            },
          ],
        },
        {
          featureType: "road",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#98a5be",
            },
          ],
        },
        {
          featureType: "road",
          elementType: "labels.text.stroke",
          stylers: [
            {
              color: "#1d2c4d",
            },
          ],
        },
        {
          featureType: "road.highway",
          elementType: "geometry",
          stylers: [
            {
              color: "#2c6675",
            },
          ],
        },
        {
          featureType: "road.highway",
          elementType: "geometry.fill",
          stylers: [
            {
              color: "#9d2a80",
            },
          ],
        },
        {
          featureType: "road.highway",
          elementType: "geometry.stroke",
          stylers: [
            {
              color: "#9d2a80",
            },
          ],
        },
        {
          featureType: "road.highway",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#b0d5ce",
            },
          ],
        },
        {
          featureType: "road.highway",
          elementType: "labels.text.stroke",
          stylers: [
            {
              color: "#023e58",
            },
          ],
        },
        {
          featureType: "transit",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#98a5be",
            },
          ],
        },
        {
          featureType: "transit",
          elementType: "labels.text.stroke",
          stylers: [
            {
              color: "#1d2c4d",
            },
          ],
        },
        {
          featureType: "transit.line",
          elementType: "geometry.fill",
          stylers: [
            {
              color: "#283d6a",
            },
          ],
        },
        {
          featureType: "transit.station",
          elementType: "geometry",
          stylers: [
            {
              color: "#3a4762",
            },
          ],
        },
        {
          featureType: "water",
          elementType: "geometry",
          stylers: [
            {
              color: "#0e1626",
            },
          ],
        },
        {
          featureType: "water",
          elementType: "labels.text.fill",
          stylers: [
            {
              color: "#4e6d70",
            },
          ],
        },
      ],
    };
    let map = new window.google.maps.Map(
      document.getElementById("map"),
      mapOptions
    );

    var locations = [
      [
        "<h4 class = 'markerLoc'>부산은행 전포역지점</h4>",
        35.15682587449451,
        129.0594747199729,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 본점</h4>",
        35.14570387700273,
        129.06613268630375,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 일광지점</h4>",
        35.26636126102917,
        129.22604509544507,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 수원지점</h4>",
        37.263876523268415,
        127.03255803787242,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 홍대역지점</h4>",
        37.55614255511305,
        126.92349410452528,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 잠실지점</h4>",
        37.50854056348289,
        127.07969767308786,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 성수동지점</h4>",
        37.544324642620026,
        127.0545273069094,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 서울CIB센터</h4>",
        37.52424351995697,
        126.92483612616192,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 구로디지털지점</h4>",
        37.48387203218616,
        126.89559833649997,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 부천지점</h4>",
        37.50701147637785,
        126.75394223533597,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 시화공단지점</h4>",
        37.334759638764545,
        126.73311334137071,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 대전영업부</h4>",
        36.351148305091534,
        127.38097210554466,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 대구지점</h4>",
        35.85479690903696,
        128.55036677004554,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 마산지점</h4>",
        35.21689007060669,
        128.60669608110925,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 창원지점</h4>",
        35.223015815912035,
        128.6787643991775,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 녹산중앙지점</h4>",
        35.09049991608398,
        128.85434209124168,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 울산호계지점</h4>",
        35.632394621507636,
        129.35057420359882,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 용원지점</h4>",
        35.10126176866726,
        128.80998190384315,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 녹산공단금융센터</h4>",
        35.09047076270102,
        128.85433320776443,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 진영지점</h4>",
        35.29445493875202,
        128.76361436648918,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 사하구청영업소</h4>",
        35.10446929535522,
        128.9745326775397,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 동아대학교영업소</h4>",
        35.114322239888985,
        128.96520139292815,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 김해주촌공단지점</h4>",
        35.21235745128279,
        128.8306980571865,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 신라대학교영업소</h4>",
        35.16956657986894,
        128.9968974097567,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 장유지점</h4>",
        35.19112924491204,
        128.80356141322372,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 부산세관영업소</h4>",
        35.10495850833038,
        129.03900291809097,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 화전공단지점</h4>",
        35.103635130472526,
        128.88239501500584,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 명지지점</h4>",
        35.09826352775294,
        128.9203378347879,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 다대2동영업소</h4>",
        35.06372504769306,
        128.98070522772477,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 신평역영업소</h4>",
        35.098700205364764,
        128.96019071247503,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 무거동지점</h4>",
        35.54772012033571,
        129.26268806382816,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 사상구청영업소</h4>",
        35.152617936902516,
        128.99059083346188,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 강서산단지점</h4>",
        35.13753456706519,
        128.856941540577,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 야음동지점</h4>",
        35.52470803680019,
        129.3308425837439,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 몰운대지점</h4>",
        35.04899692801904,
        128.96508135512212,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 언양지점</h4>",
        35.55772327154121,
        129.11989608992187,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 감천중앙지점</h4>",
        35.09024357546694,
        128.99820925170613,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 감천동지점</h4>",
        35.090243620635945,
        128.9982065117844,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 울산금융센터</h4>",
        35.515510920839816,
        129.31068927122925,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 서구청영업소</h4>",
        35.0971470571804,
        129.02344096923426,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 울산중앙지점</h4>",
        35.55477030581897,
        129.32334123396743,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행365코너 탑마트반송점</h4>",
        35.22967603759965,
        129.15047706348153,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 삼계동지점</h4>",
        35.26078669203171,
        128.8692044147634,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 당리동지점</h4>",
        35.10311181277613,
        128.97405306961352,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 봉래동영업소</h4>",
        35.09240042480048,
        129.04423258842118,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 신평동금융센터</h4>",
        35.090967588854035,
        128.9734066641657,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 다대포지점</h4>",
        35.057818783817176,
        128.97110147909802,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 중구청영업소</h4>",
        35.106710418216444,
        129.03261762208763,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 내외동지점</h4>",
        35.2325000383849,
        128.86501567221183,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 영도구청영업소</h4>",
        35.09022102501732,
        129.06712848856725,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 아미동영업소</h4>",
        35.100190280666105,
        129.0169835684226,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 삼산동지점</h4>",
        35.538729145120975,
        129.33593085074668,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 명지국제신도시지점</h4>",
        35.09829735346177,
        128.92033588690603,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 김해공항지점</h4>",
        35.172626245605585,
        128.94736425081325,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 김해금융센터</h4>",
        35.22870144736189,
        128.88219123098105,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 송도지점</h4>",
        35.0786702255678,
        129.01630011212924,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 장림동지점</h4>",
        35.08080748836602,
        128.96920152885102,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 괘법동영업소</h4>",
        35.16873012939487,
        128.97978391921086,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 북구청영업소</h4>",
        35.19703579497623,
        128.98968991474075,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 동김해지점</h4>",
        35.23376662280987,
        128.90461877130303,
      ],
      [
        "<h4 class = 'markerLoc'>부산은행 충무동지점</h4>",
        35.09556632410455,
        129.02460528178827,
      ],
    ];
    var infowindow = new google.maps.InfoWindow({
      minWidth: 150,
    });
    var marker, i;
    for (i = 0; i < locations.length; i++) {
      marker = new google.maps.Marker({
        position: new google.maps.LatLng(locations[i][1], locations[i][2]),
        map: map,
        icon: "http://drive.google.com/uc?export=view&id=1kZurfFFP7w-7lQnDYLli6HAojH-y7jGF",
      });

      google.maps.event.addListener(
        marker,
        "click",
        (function (marker, i) {
          return function () {
            infowindow.setContent(locations[i][0]);
            infowindow.open(map, marker);
          };
        })(marker, i)
      );
    }
    // let marker = new window.google.maps.Marker({
    //   position: { lat: 37.509622300000075, lng: 127.04202689999946 },
    // });
    // let marker2 = new window.google.maps.Marker({
    //   position: { lat: 37.48816199999984, lng: 126.99830879999988 },
    // });

    // // To add the marker to the map, call setMap();
    // marker.setMap(map);
    // marker2.setMap(map);
  },
};
</script>
<style>
.markerLoc {
  color: black !important;
  margin-top: 10 !important;
}
</style>
