# OneWebAttachefileJS
Sample java script attache file in oneweb

function inputitem (){
 // window.myScope.State.item =  $('#input4').val();
   window.myScope.update();
    console.log('---->>'+window.myScope.State.item);
    $("#input4").trigger("blur");//re call MF
}
function setBase64Val(){

 console.log('---->>'+window.myScope.State.photo);
 console.log('---->>'+window.myScope.State.image1);

}
function initOnChangePhoto(){

  initHolder();

}

function initHolder(){
  var holder = document.getElementById('holder');
    holder.ondragover = function () { this.className = 'hover'; return false; };
    holder.ondrop = function (e) {
      this.className = 'hidden';
      e.preventDefault();
      var file = e.dataTransfer.files[0];
      var reader = new FileReader();
      reader.onload = function (event) {
          document.getElementById('image_droped').className='visible'
          $('#image_droped').attr('src', event.target.result);
          window.myScope.State.photo = event.target.result;
          window.myScope.update();
      }
      reader.readAsDataURL(file);
    };
  //image1
    var image1 = document.getElementById('image1');
    image1.ondragover = function () { this.className = 'hover'; return false; };
    image1.ondrop = function (e) {
      this.className = 'hidden';
      e.preventDefault();
      var file = e.dataTransfer.files[0];
      var reader = new FileReader();
      reader.onload = function (event) {
          document.getElementById('image1_droped').className='visible'
          $('#image1_droped').attr('src', event.target.result);
          window.myScope.State.image1 = event.target.result;
          window.myScope.update();
      }
      reader.readAsDataURL(file);
    };
}

