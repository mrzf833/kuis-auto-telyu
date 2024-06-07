# kuis-auto-telyu

masukan kode dibawah ini ke dalam inspect elemen pas di menu pilihan kuis

```
Array.prototype.random = function () {
  return this[Math.floor((Math.random()*this.length))];
}

let list_berapa_pilihan = []
$('div[id="radioX"]').each(function(index, value) {

  let panjangPilihan =  $(`div[id='radioX']:eq(${index}) li`).size();
  list_berapa_pilihan.push(panjangPilihan)
});
list_berapa_pilihan = [... new Set(list_berapa_pilihan)]



let list_pengisian = []
list_berapa_pilihan.forEach((value, index) => {
  let option = prompt("INI UNTUK PENGISIAN " + value + " PILIHAN.\nmasukan pilihan yang di mau. mulai dari atas dan dari 0. contoh input satu pilihan = 0. contoh pilihan random = 0,1,2");
  option = option.replaceAll(' ','');

  let options = option.split(",");
  list_pengisian[value] = options
});

$('div[id="radioX"]').each(function(index, value) {
  let panjangPilihan =  $(`div[id='radioX']:eq(${index}) li`).size();

  let get_pilihan = list_pengisian[panjangPilihan];
  console.log
  let terpilih = get_pilihan.random()


  if(terpilih > (panjangPilihan - 1)){
      alert("option tidak ada");
      $(`div[id='radioX'] li input`).attr('checked', false);
      return false;
  }

  $(`div[id='radioX']:eq(${index}) li:eq(${terpilih}) input`).attr('checked', true);
});

```
