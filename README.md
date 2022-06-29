# kuis-auto-telyu

masukan kode ini ke dalam inspect elemen

Array.prototype.random = function () {
  return this[Math.floor((Math.random()*this.length))];
}

let option = prompt("masukan pilihan yang di mau. mulai dari atas dan dari 0. contoh input satu pilihan = 0. contoh pilihan random = 0,1,2");
option = option.replaceAll(' ','');


$('div[id="radioX"]').each(function(index, value) {
  $(`div[id='radioX']:eq(${index}) li:eq(${option}) input`).attr('checked', 'checked');
});
