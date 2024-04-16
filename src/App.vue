git
<script setup>
import { ref } from "vue"
import html2canvas from 'html2canvas';
import jsPDF from 'jspdf'
import autoTable from 'jspdf-autotable'
import Swal from 'sweetalert2'


let conjunto = ref([
  { id: "00", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "01", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "02", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "03", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "04", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "05", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "06", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "07", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "08", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "09", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "10", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "11", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "12", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "13", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "14", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "15", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "16", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "17", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "18", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "19", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "20", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "21", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "22", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "23", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "24", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "25", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "26", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "27", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "28", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "29", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "30", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "31", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "32", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "33", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "34", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "35", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "36", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "37", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "38", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "39", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "40", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "41", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "42", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "43", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "44", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "45", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "46", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "47", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "48", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "49", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "50", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "51", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "52", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "53", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "54", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "55", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "56", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "57", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "58", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "59", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "60", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "61", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "62", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "63", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "64", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "65", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "66", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "67", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "68", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "69", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "70", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "71", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "72", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "73", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "74", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "75", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "76", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "77", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "78", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "79", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "80", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "81", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "82", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "83", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "84", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "85", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "86", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "87", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "88", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "89", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "90", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "91", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "92", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "93", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "94", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "95", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "96", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "97", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "98", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
  { id: "99", premio: "", valor: 0, nombre: "", fecha: "", estado: 2 },
]);

let guard2 = ref("");
let enlistadovalue = ref("");
let cambiocolor = ref("");
let pintar = ref("");
let premio = ref("");
let valor = ref("");
let nombre = ref("");
let telefono = ref("");
let direccion = ref("");
let fecha = ref("");
let estado = ref("");
let guard = ref("");
let enlis = ref([]);
let deshabi = ref("");
let letra_color = ref("#ffffff");
let boton = ref("#06113C");
let bordes = ref("3px solid #58287F");
let fondo_cuadrilla = ref("#3b3453");
document.body.style.backgroundColor = "rgb(41, 34, 60)";
let hover = ref("#6f6396");
let fondo_modal = ref("#3a4250");
let fondo = ref("");
let loteria = ref("");
let numeroGanador = ref("");
let id = ref("");
let des = ref(false);
let inicio = ref(true);
let mj= ref(false);


  

function clasico() {
  fondo_modal = "#5b6980";
  hover = "#4a6e86";
  fondo_cuadrilla = "#ced6e0";
  letra_color.value = "black";
  bordes.value = "3px solid #000";
  boton.value = "#1c7c97";
  document.body.style.backgroundColor = "rgb(184, 203, 219)";
  console.log(fondo.value, letra_color.value, boton.value);
}

function azul() {
  fondo_modal = "#435471";
  hover = "rgb(2, 182, 214)";
  fondo_cuadrilla = "#00ccff";
  bordes.value = "1px solid #ffffff ";
  letra_color.value = "#000000";
  boton.value = "rgb(0, 215, 255)";
  document.body.style.backgroundColor = " rgb(52, 114, 190)";
  console.log(fondo.value, letra_color.value, boton.value);
}
function pink() {
  fondo_modal = "#9860d0";
  hover = "#f4a3ff";
  fondo_cuadrilla = "#D09CFA";
  bordes.value = "3px solid #8690ff ";
  letra_color.value = "#00000";
  boton.value = "#E11299";
  document.body.style.backgroundColor = "rgb(254, 222, 255)";
  console.log(fondo.value, letra_color.value, boton.value);
}
function dark() {
  fondo_modal = "#3a4250";
  hover = "#6f6396";
  fondo_cuadrilla = "#3b3453";
  bordes.value = "3px solid #58287F ";
  letra_color.value = "#ffffff";
  boton.value = "#06113C";
  document.body.style.backgroundColor = "rgb(41, 34, 60)";
  console.log(fondo.value, letra_color.value, boton.value);
}

function actualizar() {
  if (enlistadovalue.value == 1) {
    for (let i = 0; i <= 99; i++) {
      enlis.value.pop();
    }

    for (let i = 0; i <= 99; i++) {
      if (conjunto.value[i].estado == 1) {
        enlis.value.push({
          nombre: conjunto.value[i].nombre,
          telefono: conjunto.value[i].telefono,
          direccion: conjunto.value[i].direccion,
          id: conjunto.value[i].id,
          estado: conjunto.value[i].estado,
        });
      }
    }
  } else if (enlistadovalue.value == 2) {
    for (let i = 0; i <= 99; i++) {
      enlis.value.pop();
    }

    for (let i = 0; i <= 99; i++) {
      if (conjunto.value[i].estado == 2) {
        enlis.value.push({
          nombre: conjunto.value[i].nombre,
          telefono: conjunto.value[i].telefono,
          direccion: conjunto.value[i].direccion,
          id: conjunto.value[i].id,
          estado: conjunto.value[i].estado,
        });
      }
    }
  } else if (enlistadovalue.value == 3) {
    for (let i = 0; i <= 99; i++) {
      enlis.value.pop();
    }

    for (let i = 0; i <= 99; i++) {
      if (conjunto.value[i].estado == 3) {
        enlis.value.push({
          nombre: conjunto.value[i].nombre,
          telefono: conjunto.value[i].telefono,
          direccion: conjunto.value[i].direccion,
          id: conjunto.value[i].id,
          estado: conjunto.value[i].estado,
        });
      }
    }
  }
}

function captureScreen() {
  html2canvas(document.querySelector("#contenedor")).then((canvas) => {
    const link = document.createElement("a");

    link.href = canvas.toDataURL("image/png");

    link.download = "screenshot.png";

    link.click();
  });
}

function sacar() {
  deshabi.value = false;
  for (let i = 0; i <= 99; i++) {
    enlis.value.pop();
  }
}

function editar(p, i) {
  des.value = true;
  nombre.value = p.nombre;
  telefono.value = p.telefono;
  direccion.value = p.direccion;
  estado.value = p.estado;
  guard.value = p.id;
  guard2.value = i;
}

function cam() {
  if (!des.value) {
    // Si des.value es falso, no haces nada
    return;
  }

  let expresionnombre = /^[a-zA-Z\s]+$/;
  let verifinombre = expresionnombre.test(nombre.value);

  let expresiontel = /^\d{8,}$/;
  let verifitel = expresiontel.test(telefono.value);

  let expresiondir = /^[a-zA-Z0-9\s!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]+$/;
  let verifidir = expresiondir.test(direccion.value);

  if (!verifinombre) {
    pintar.value = "Llena el campo Nombre";
    cambiocolor.value = "background-color:#ff4d4d;";
  } else if (!verifitel) {
    pintar.value = "Debes llenar  Teléfono";
    cambiocolor.value = "background-color:#ff4d4d;";
  } else if (!verifidir) {
    pintar.value = "Completa el campo  Dirección";
    cambiocolor.value = "background-color:#ff4d4d;";
  } else {
    // Actualizar el valor de conjunto.value[guard2.value] una vez, sin necesidad de un bucle
    conjunto.value[guard2.value].nombre = nombre.value;
    conjunto.value[guard2.value].telefono = telefono.value;
    conjunto.value[guard2.value].direccion = direccion.value;
    conjunto.value[guard2.value].estado = estado.value;

    pintar.value = "Registro exitoso.";
    cambiocolor.value = "background-color:#0be881;";

    setTimeout(() => {
      cambiocolor.value = "";
      pintar.value = "";
    }, 3000);

    document.getElementById("close").click();

    // Limpiar los campos de entrada después de editar
    nombre.value = "";
    telefono.value = "";
    direccion.value = "";
    estado.value = "";
    guard.value = "";
    guard2.value = "";
  }
  console.log("conjunto");
  console.log(conjunto.value);
  console.log("conjunto");
  let prueba = conjunto.value.filter((a) => {
    return a.estado === "3";
  });
  console.log("prueba");
  console.log(prueba);
  console.log("prueba");
}

function camgeneral() {
  mj.value=true
  inicio.value = true;
  let expresionvalor = /^\d+(\.\d{1,2})?$/;
  let verifivalor = expresionvalor.test(valor.value);

  let expresionfecha = /^(?!\s*$)\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01])$/;
  let verififecha = expresionfecha.test(fecha.value);
  let fechaActual = new Date().toISOString().slice(0, 10);
  let fechaValida = fecha.value >= fechaActual;

  let expresionpremio = /^[^\s]+( [^\s]+)*$/;
  let verifipremio = expresionpremio.test(premio.value);

  let veriloteria = loteria.value;

  if (verifipremio === false) {
    pintar.value = "Llena el campo Premio";
    cambiocolor.value = "background-color:#ff4d4d;";
    setTimeout(() => {
      cambiocolor.value = "";
      pintar.value = "";
    }, 3000);
  } else if (verifivalor === false) {
    pintar.value = "Llena el campo Valor";
    cambiocolor.value = "background-color:#ff4d4d;";
    setTimeout(() => {
      cambiocolor.value = "";
      pintar.value = "";
    }, 3000);
  } else if (verififecha === false || !fechaValida) {
    pintar.value = "Fecha inválida.";
    cambiocolor.value = "background-color:#ff4d4d;";
  } else if (veriloteria === "") {
    pintar.value = "Seleccionar una loteria";
    cambiocolor.value = "background-color:#ff4d4d;";
    setTimeout(() => {
      cambiocolor.value = "";
      pintar.value = "";
    }, 3000);
  } else {
    for (let i = 0; i <= 99; i++) {
      conjunto.value[i].valor = valor.value;
      conjunto.value[i].premio = premio.value;
      conjunto.value[i].fecha = fecha.value;
      conjunto.value[i].loteria = loteria.value;
    }

    pintar.value = "Cambio exitoso.";
    cambiocolor.value = "background-color:#0be881;";
    setTimeout(() => {
      cambiocolor.value = "";
      pintar.value = "";
    }, 3000);
  }
}


const talonario = [];



function seleccionarGanador() {
  if (numeroGanador.value === "") {
    console.log("Debe Ingresar el número ganador");
    
  } else {
    for (let i = 0; i < conjunto.value.length; i++) {
        const convertir = parseInt(numeroGanador.value);
        conjunto.value[convertir].estado = '4';
        if (conjunto.value[i].estado === '4') {
          cambiocolor.value = "Green";
        }
    }Swal.fire("El ganador es el número " + numeroGanador.value);
  }

  
}


function generarPDF() {
  const doc = new jsPDF();

  doc.text("Talonario", 90, 10);
  doc.text(`Fecha del Sorteo: ${fecha.value}`, 10, 30);
  doc.text(`Ganador: ${numeroGanador.value}`, 10, 40);
  doc.text(`Lotería: ${loteria.value}`, 100, 30);

  
  let sumaBoletasDebe = 0;
  let sumaBoletasEnJuego = 0;

  const headers = [["Nombre", "Teléfono", "Dirección", "N° boleta", "Valor", "Estado"]];
  const data = [];

  for (let i = 0; i < conjunto.value.length; i++) {
    const boleta = conjunto.value[i];
    if (boleta.estado === '1' || boleta.estado === '3') {
      data.push([
        boleta.nombre,
        boleta.telefono,
        boleta.direccion,
        boleta.id,
        boleta.valor.toLocaleString(), 
        boleta.estado === '1' ? "Vendido" : "Debe"
      ]);

      if (boleta.estado === '3') {
        sumaBoletasDebe += boleta.valor;
      } else if (boleta.estado === '1') {
        sumaBoletasEnJuego += boleta.valor;
      }
    }
  }

 
  const premioFormateado = parseFloat(premio.value).toLocaleString();
  doc.text(`Premio: ${premioFormateado}`, 100, 40);

 
  const sumaBoletasDebeFormateada = sumaBoletasDebe.toLocaleString();
  const sumaBoletasEnJuegoFormateada = sumaBoletasEnJuego.toLocaleString();

  doc.autoTable({
    startY: 50,
    head: headers,
    body: data,
  });

  doc.text(`Suma de Boletas que Deben: ${sumaBoletasDebeFormateada}`, 10, doc.autoTable.previous.finalY + 10);
  doc.text(`Suma de Boletas en Juego: ${sumaBoletasEnJuegoFormateada}`, 10, doc.autoTable.previous.finalY + 20);

  doc.save("talonario.pdf");
}









function formatoConUnidades(numero) {
    return numero.toString().replace(/\B(?=(\d{3})+(?!\d))/g, "."); 
}

</script>

<template>
  <div class="contenedor">
    <header>TALONARIO</header>

    <div class="opciones">
      <div type="button" data-bs-toggle="modal" data-bs-target="#enlistados">
        <img src="../src/assets/recursos_pag_loteria/enlistar.png" alt="" />
        <p>Enlistar puestos</p>
      </div>

      <div
        type="button"
        data-bs-toggle="modal"
        data-bs-target="#exampleModal"
        id="personalizar"
      >
        <img src="../src/assets/recursos_pag_loteria/personalizar.png" alt="" />
        <p>Personalizar</p>
      </div>

      <div type="button" @click="captureScreen()" id="generar_archivo">
        <img src="../src/assets/recursos_pag_loteria/imagen.png" alt="" />
        <p>Guardar imagen</p>
      </div>
      <div type="button" @click="generarPDF()" id="generarPDF">
        <img src="../src/assets/recursos_pag_loteria/pdf.png" alt="" />
        <p>Generar PDF</p>
      </div>
<!---->
      <div type="button" @click="seleccionarGanador()" class="Ganador">
        <img src="../src/assets/recursos_pag_loteria/balota.jpg" alt="" />
        <p>Escribir No Ganador: <input type="text" id="numeroGanador" placeholder="Escribe el número" v-model="numeroGanador"></p>
        
      </div>

    </div>
    
    <div class="datos">
      <div
        type="button"
        class="general"
        data-bs-toggle="modal"
        data-bs-target="#3"
      >
        INFORMACIÓN
      </div>
      <div class="premio">
        <p>🏆{{ formatoConUnidades(premio) }}</p>
      </div>
      <div class="valor_loteria">
        >
        <p>💲{{ formatoConUnidades(valor) }}</p>
      </div>
      <div class="fecha">
        <p>🗓️{{ fecha }}</p>
      </div>
      <div class="nombre_loteria">
        <img
          src="../src/assets/recursos_pag_loteria/banco_nombrebanco.png"
          alt=""
        />
        <p>{{ loteria }}</p>
      </div>
     
    </div>

    <div
      class="modal fade"
      id="2"
      data-bs-backdrop="static"
      data-bs-keyboard="false"
      tabindex="-1"
      aria-labelledby="staticBackdropLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog" v-show="des">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="staticBackdropLabel">
              Estas editando la boleta {{ guard }}
            </h1>
            <button
              id="close"
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
              style="background-color: white"
            ></button>
          </div>
          <div class="modal-body">
            <input
              v-model="nombre"
              placeholder="👨‍🎓Ingresa el nombre del comprador"
              type="text"
            /><br />
            <input
              v-model="telefono"
              placeholder="📲Ingresa el telefono del comprador"
              type="phone"
            /><br />
            <input
              v-model="direccion"
              placeholder="🏡Ingresa el direccion del comprador"
              type="text"
            /><br />
            <select v-model="estado">
              <option style="color: green" value="1">Jugando</option>
              <option style="color: blue" value="2">Disponible</option>
              <option style="color: red" value="3">En deuda</option>
            </select>
          </div>
          <div class="modal-footer">
            <div style="display: flex">
              <h1
                style="
                  font-size: 20px;
                  border-radius: 10px;
                  height: 35px;
                  margin-right: 50px;
                  padding: 5px;
                  width: 300px;
                  text-align: center;
                "
                v-bind:style="cambiocolor"
              >
                {{ pintar }}
              </h1>
              <button class="btn btn-primary" @click="cam()">guardar</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div
      class="modal fade"
      id="3"
      data-bs-backdrop="static"
      data-bs-keyboard="false"
      tabindex="-1"
      aria-labelledby="staticBackdropLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog" v-show="inicio">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="staticBackdropLabel">
              Edicion Global
            </h1>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-body">
            <p>Premio</p>
            <input
              v-model="premio"
              placeholder="Ingresa el premio"
              type="text"
            />
            <p>valor boleta</p>
            <input
              v-model="valor"
              placeholder="valor de la boleta"
              type="number"
            />
            <p>Fecha Fin</p>
            <input
              v-model="fecha"
              placeholder="Fecha en la que juega"
              type="date"
            />
            <p>Loteria</p>

            <select name="loteria" v-model="loteria">
              <br /><br />
              <option value="santander">Santander</option>
              <option value="bogota">Bogotá</option>
              <option value="cruzroja">Cruz Roja</option>
              <option value="cundinamarca">Cundinamarca</option>
              <option value="manizales">Manizales</option>
            </select>
          </div>
          <div class="modal-footer">
            <div style="display: flex">
              <h1
                style="
                  font-size: 20px;
                  border-radius: 10px;
                  height: 35px;
                  margin-right: 50px;
                  padding: 5px;
                  width: 300px;
                  text-align: center;
                "
                v-bind:style="cambiocolor"
              >
                {{ pintar }}
              </h1>
              <button class="btn btn-primary" @click="camgeneral()">
                guardar
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div
    class="modal fade"
    id="enlistados"
    data-bs-backdrop="static"
    data-bs-keyboard="false"
    tabindex="-1"
    aria-labelledby="staticBackdropLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-scrollable">
      <div class="modal-content">
        <div class="modal-header">
          <h1
            style="display: flex"
            class="modal-title fs-5"
            id="staticBackdropLabel"
          >
            <p style="padding-right: 45px; font-size: 20px">
              Elije uno de los estados:
            </p>
            <select v-model="enlistadovalue" @change="actualizar">
              <option style="color: #1dd1a1" value="1">Jugando</option>
              <option style="color: blue" value="2">Disponible</option>
              <option style="color: red" value="3">En deuda</option>
            </select>
          </h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            @click="sacar()"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <table class="table table-hover">
            <thead class="table-dark">
              <tr>
                <td>Nombre</td>
                <td>Telefono</td>
                <td>Direccion</td>
                <td>#Puesto</td>
                <td>Estado</td>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(p, i) in enlis" :key="i">
                <td>
                  <b>{{ p.nombre }}</b>
                </td>
                <td>
                  <b>{{ p.telefono }}</b>
                </td>
                <td>
                  <b>{{ p.direccion }}</b>
                </td>
                <td>
                  <b>{{ p.id }}</b>
                </td>
  
                <td>
                  <b style="color: red" v-if="p.estado == 3">En deuda</b>
                  <b style="color: blue" v-else-if="p.estado == 2"
                    >Disponible</b
                  >
                  <b style="color: #1dd1a1" v-else-if="p.estado == 1"
                    >En juego</b
                  >
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-secondary"
            @click="sacar()"
            data-bs-dismiss="modal"
          >
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
  

    <div id="contenedor" class="cuadrilla" v-if="mj">
      <div v-for="(p, i) in conjunto" id="conjunto_numeros" :key="i">
        <!-- Buttv-on modal -->
        <button
          v-if="p.estado == 1"
          style="background-color: #57ebc3"
          @click="editar(p, i)"
          type="button"
          id="numeros"
          class="btn btn-light"
          data-bs-toggle="modal"
          data-bs-target="#1"
        >
          {{ p.id }}
        </button>

        <button
          v-if="p.estado == 2"
          style="background-color: blue"
          @click="editar(p, i)"
          type="button"
          id="numeros"
          class="btn btn-light"
          data-bs-toggle="modal"
          data-bs-target="#1"
        >
          {{ p.id }}
        </button>

        <button
          v-if="p.estado == 3"
          style="background-color: red"
          @click="editar(p, i)"
          type="button"
          id="numeros"
          class="btn btn-light"
          data-bs-toggle="modal"
          data-bs-target="#1"
        >
          {{ p.id }}
        </button>

        <button
          v-if="p.estado == 4"
          style="background-color: yellow"
          type="button"
          id="numeros"
          class="btn btn-light"
          data-bs-toggle="modal"
          data-bs-target="#1"
        >
          {{ p.id }}
        </button>

        <!-- Modal -->
        <div
          class="modal fade"
          id="1"
          data-bs-backdrop="static"
          data-bs-keyboard="false"
          tabindex="-1"
          aria-labelledby="staticBackdropLabel"
          aria-hidden="true"
        >
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h1 class="modal-title fs-5" id="staticBackdropLabel">
                  Informacion de la boleta{{ guard }}
                </h1>
                <button
                color="yellow"
                  type="button"
                  class="btn-close"
                  data-bs-dismiss="modal"
                  aria-label="Close"
                ></button>
              </div>
              <div id="modal_b" class="modal-body">
                <div><b>PREMIO:</b> {{ premio }}</div>
                <div><b>VALOR BOLETA:</b> {{ valor }}</div>
                <div><b>NOMBRE DEL COMPRADOR:</b> {{ nombre }}</div>
                <div><b>TELEFONO:</b> {{ telefono }}</div>
                <div><b>DIRECCION:</b> {{ direccion }}</div>
                <div><b>FECHA:</b> {{ fecha }}</div>
                <div style="display: flex">
                  <b style="margin-right: 5px">ESTADO: </b>
                  <div style="color: #1dd1a1" v-if="estado == 1">En juego</div>
                  <div style="color: blue" v-else-if="estado == 2">
                    Disponible
                  </div>
                  <div style="color: red" v-else>En deuda</div>
                </div>

                <div
                  style="margin-left: 10px"
                  type="button"
                  class="btn btn-primary"
                  data-bs-toggle="modal"
                  data-bs-target="#2"
                >
                  Editar
                </div>
              </div>
              <div class="modal-footer"></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Modal -->
      <div
        class="modal fade"
        id="exampleModal"
        tabindex="-1"
        aria-labelledby="exampleModalLabel"
        aria-hidden="true"
      >
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h1 class="modal-title fs-5" id="exampleModalLabel">
                Personalizar
              </h1>
              <button
                type="button"
                class="btn-close"
                data-bs-dismiss="modal"
                aria-label="Close"
              ></button>
            </div>
            <div class="modal-body">
              seleccionar tema
              <div class="temas">
                <div class="tema clasico" @click="clasico()">Clasico</div>
                <div class="tema azul" @click="azul()">Azul</div>
                <div class="tema pink" @click="pink()">Pink ice</div>
                <div class="tema dark" @click="dark()">Noche</div>
              </div>
            </div>
            <div class="modal-footer">
              <button
                type="button"
                class="btn btn-secondary"
                data-bs-dismiss="modal"
              >
                cerrar
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
b {
  color: #fff;
}

input {
  border-radius: 10px;
}

select {
  border-radius: 10px;
}

body {
  display: flex;
  justify-content: center;
  overflow: hidden;
  background-color: v-bind(fondo);
}

header {
  position: relative;
  font-size: 3rem;
  left: 5vw;
  color: v-bind(letra_color);
}

.opciones {
  position: relative;
  left: 175%;
  width: 30vw;
  top: 3vh;
  z-index: 5;
}

.opciones div {
  background-color: v-bind(boton);
  margin: 5px;
  border-radius: 5px;
  transition: all 1s;
  height: 70px;
}

.opciones div:hover {
  transform: translateX(-100px);
  cursor: pointer;
}

.opciones p {
  opacity: 0%;
  transition: all 0.5s;
  position: relative;
  top: -40px;
  left: 100px;
  font-size: 17px;
  font-weight: 700;
  color: v-bind(letra_color);
}

.opciones:hover p {
  opacity: 100%;
  left: 90px;
}

.opciones img {
  position: relative;
  width: 60px;
  height: 60px;
  padding: 5px;
  left: 10px;
}

.datos {
  position: relative;
  bottom: 60vh;
  right: 60vh;
}

.datos div {
  margin: 25px;
  padding: 10px;
  width: 200px;
  border-radius: 25px;
  border: v-bind(bordes);
  transition: all 0.2s;
  cursor: pointer;
}

.datos div:hover {
  background-color: v-bind(hover);
  scale: 1.05;
}

.datos img {
  display: block;
  margin: 0 auto;
  width: 50px;
  height: 50px;
}

.datos p {
  display: block;
  text-align: center;
  font-size: 20px;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  margin-top: -5%;
  color: v-bind(letra_color);
}

.cuadrilla {
  top: 10vh;
  left: 70vh;
  width: 90vh;
  height: 85vh;
  display: flex;
  flex-wrap: wrap;
  background: v-bind(fondo_cuadrilla);
  border: v-bind(bordes);
  border-radius: 11px;
  position: absolute;
  cursor: pointer;
  padding: 20px;
  padding-bottom: 40px;
  margin-top: 1%;
  margin-bottom: 30%;
}

#conjunto_numeros {
  display: inline-block;
  width: 10%;
  margin-top: 5px;
}

#conjunto_numeros button {
  width: 7vh;
  height: 7vh;
  border-radius: 50%;
}

.editar {
  cursor: pointer;
}

.marcar {
  background-color: #ccffd7;
  width: 150px;
  cursor: pointer;
}

.marcar input {
  width: 25px;
  height: 25px;
  cursor: pointer;
}

#boton_editar_rifa {
  background-color: rgb(185, 103, 210);
  border: solid rgb(214, 193, 232);
  position: absolute;
  top: 0;
}

.modal-body p {
  font-size: 17px;
  font-weight: 400;
  margin: 0;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}

.modal-body input {
  margin: 15px 0px 15px 0px;
  border: solid 1px rgb(185, 164, 189);
  width: 200px;
  height: 30px;
}

.modal-body input:focus {
  outline: solid 0.5px rgb(185, 164, 189);
}

.temas {
  display: flex;
}

.tema {
  display: flex;
  border: solid 1px;
  width: 100px;
  height: 90px;
  margin: 10px;
  justify-content: center;
  align-items: center;
  text-align: center;
  border-radius: 10px;
  transition: all 0.5s;
}

.tema:hover {
  scale: 1.02;
}

.clasico {
  border-color: #000000;
  color: #000000;
  background-color: #eee7e7;
}

.clasico:hover {
  background-color: #bfbfbf;
  color: rgb(0, 0, 0);
  border-color: rgb(206, 206, 206);
}

.azul {
  border-color: rgba(99, 99, 237, 0.544);
  color: rgba(17, 25, 239, 0.292);
  background-color: rgb(147, 147, 252);
}

.azul:hover {
  background-color: rgb(105, 105, 255);
  color: rgb(217, 217, 255);
}

.pink {
  border-color: #000000;
  color: #000000;
  background-color: rgb(255, 193, 193);
}

.pink:hover {
  background-color: #d08ded;
  color: rgb(61, 226, 255);
  border-color: whitesmoke;
}

.dark:hover {
  background-color: black;
  color: rgb(154, 72, 255);
}
.general {
  background: v-bind(boton);
  color: v-bind(letra_color);
}

.a {
  color: #5b6980;
}

.modal-content {
  background-color: v-bind(fondo_modal);
}

.modal-content input {
  width: 300px;
  height: 40px;
}
.modal-content p {
  color: v-bind(letra_color);
  font-size: 15px;
}

.modal-content p,
input,
select {
  position: relative;
  left: 20px;
}

select {
  height: 35px;
}

input {
  font-size: 15px;
}

.modal-content h1 {
  color: v-bind(letra_color);
}

#modal_b div {
  margin-bottom: 20px;
  color: v-bind(letra_color);
  font-weight: 600;
}

.l {
  color: rgb(184, 203, 219);
}

.btn-close {
 
  color: #ffffffec;
}
.Ganador {
  /*
 display: flex;
  text-align: center;
  justify-content: center;*/
 
   color: white;
}

button {
  border-radius: 30%;
  background-color: rgba(191, 191, 248, 0.212);
  margin-right: 10%;
}

#numeroGanador {
/**/display: flex;
  text-align: center;
  justify-content:center;
  color: rgb(0, 0, 0);
  width: 35%;
  margin-bottom: 10%;
}
@media (max-width: 1250) {
  .cuadrilla {
    top: 10vh;
    left: 30vh;
    width: 70vh;
    display: flex;
    flex-wrap: wrap;
    background: v-bind(fondo_cuadrilla);
    border: v-bind(bordes);
    border-radius: 11px;
    position: absolute;
    cursor: pointer;
    padding: 15px;
    padding-bottom: 40px;
    margin: 3%;
    margin-bottom: 10vh;
  }

  .opciones {
    position: relative;
    left: 175%;
    width: 30vw;
    top: 3vh;
    z-index: 5;
  }
  .datos {
    position: relative;
    bottom: 65vh;
    left: -30vw;
  }
}
@media (max-width: 1150px) {
  .cuadrilla {
    top: 10vh;
    left: 30vh;
    width: 70vh;
    display: flex;
    flex-wrap: wrap;
    background: v-bind(fondo_cuadrilla);
    border: v-bind(bordes);
    border-radius: 11px;
    position: absolute;
    cursor: pointer;
    padding: 15px;
    padding-bottom: 40px;
    margin: 3%;
    margin-bottom: 10vh;
  }

  .opciones {
    position: relative;
    left: 175%;
    width: 30vw;
    top: 3vh;
    z-index: 5;
  }
  .datos {
    position: relative;
    bottom: 65vh;
    left: -30vw;
  }
}

@media (max-width: 1100px) {
  header {
    font-size: 2.5rem;
  }

  .opciones {
    left: 100%;
    width: 25vw;
  }

  .datos {
    bottom: 50vh;
    right: 50vh;
  }

  .cuadrilla {
    left: 60vh;
    width: 80vh;
    margin: 2%;
    margin-bottom: 5vh;
  }
}

@media (max-width: 900px) {
  .opciones {
    left: 75%;
    width: 20vw;
  }

  .datos {
    bottom: 55vh;
    right: 45vh;
  }

  .cuadrilla {
    left: 50vh;
    width: 70vh;
    margin: 1%;
    margin-bottom: 3vh;
  }
}

@media (max-width: 700px) {
  .opciones {
    left: 50%;
    width: 15vw;
  }

  .datos {
    bottom: 60vh;
    right: 40vh;
  }

  .cuadrilla {
    left: 30vh;
    width: 60vh;
    margin: 0.5%;
    margin-bottom: 1vh;
  }
}

@media (max-width: 500px) {
  header {
    font-size: 2rem;
  }

  .opciones {
    left: 25%;
    width: 10vw;
  }

  .datos {
    bottom: 65vh;
    right: 30vh;
  }

  .cuadrilla {
    left: 20vh;
    width: 50vh;
    margin: 0.25%;
    margin-bottom: 0.5vh;
  }
}

@media (max-width: 400px) {
  header {
    font-size: 2rem;
    left: 2vw;
  }

  .opciones {
    left: 150%;
    width: 40vw;
  }

  .datos {
    bottom: 70vh;
    right: 40vw;
  }

  .cuadrilla {
    top: 15vh;
    left: 20vh;
    width: 60vh;
    margin: 5%;
  }

  .opciones p {
    font-size: 15px;
  }

  .modal-content input {
    width: 250px;
  }
}

@media (max-width: 350px) {
  .opciones {
    left: 100%;
    width: 100%;
  }

  .datos {
    bottom: 70vh;
    left: -20vw;
  }

  .cuadrilla {
    top: 10vh;
    left: 10vh;
    width: 80vh;
    margin-bottom: 5vh;
  }

  .modal-content input {
    width: 200px;
  }

  .tema {
    width: 70px;
    height: 60px;
    margin: 5px;
  }
}

@media (max-width: 300px) {
  header {
    font-size: 2.5rem;
    left: 3vw;
  }

  .opciones {
    left: 150%;
    width: 25vw;
  }

  .datos {
    bottom: 70vh;
    left: -25vw;
  }

  .cuadrilla {
    top: 10vh;
    left: 5vh;
    width: 70vh;
    margin-bottom: 5vh;
  }

  .modal-content input {
    width: 150px;
  }

  .tema {
    width: 60px;
    height: 50px;
    margin: 3px;
  }
}
</style>
