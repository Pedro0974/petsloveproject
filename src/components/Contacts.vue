<template>
    <div class="container-contacts" id="contacts">

        <form class="container-form">
            <div class="flex flex-col w-full gap-8">
                <div class="flex flex-col w-full gap-2">
                    <label class="input-label">Nome do Pet</label>
                    <input class="input-field" type="text" v-model="namePet">
                </div>
                <div class="flex flex-col w-full gap-2">
                    <label class="input-label">Nome do Dono</label>
                    <input class="input-field" type="text" v-model="nameDono">
                </div>

                <div class="flex flex-col w-full gap-2">
                    <label class="input-label">Data Desejada</label>
                    <input class="input-field" type="date" />
                </div>
                <div class="flex flex-col w-full gap-2">
                    <label class="input-label">Horario Desejado</label>
                    <select class="input-field" v-model="horario">
                        <option v-for="horario in horarios" :key="horario">
                            {{ horario }}
                        </option>
                    </select>
                </div>
                <div class="flex flex-col w-full gap-2">
                    <label class="input-label">Serviço Desejado</label>
                    <select class="input-field" v-model="servico">
                        <option v-for="servico in typeServices" :key="servico">
                            {{ servico }}
                        </option>
                    </select>
                </div>

                <button class="btn-agendar" @click.prevent="submitFromWhatsapp">Agendar Via Whatsapp</button>
            </div>

            <div class=" w-full">
                <div class="flex flex-col w-full">
                    <h1 class="text-2xl font-bold text-center text-blue-800">Envie Seu Agendamento Para Confirmação em Nosso Whatsapp</h1>
                    <p class="text-center text-lg text-white ">Iremos confirmar seu agendamento com nossa escala de atendimento de
                        acordo com o horario e dia selecionado, ao enviar aguarde a confirmação dos nossos atendentes</p>
                </div>
                <div class="flex flex-col w-full mt-10">
                    <h1 class="text-2xl font-bold text-center text-blue-800">Nossas Informações</h1>
                    <div class="flex gap-2 text-white">
                        <strong>Tel:</strong><label>32999046481</label>
                    </div>
                    <div class="flex gap-2 text-white">
                        <strong>Email:</strong><label>petslovecontacts@gmail.com</label>
                    </div>
                    <div class="flex gap-2 text-white">
                        <strong>Endereço:</strong><label>Rua A - 123, Bloco 1 Muriaé</label>
                    </div>
                </div>
            </div>

        </form>

    </div>
</template>

<script>

export default {
    name: 'Contacts',

    data() {
        return {
            typeServices: [
                'Cuidado Diurno',
                'Atividades Recreativas',
                'Alimentação e Hidratação',
                'Treinamento Básico',
                'Áreas de Descanso',
                'Monitoramento de Saúde',
                'Serviços Gerais de Higiene'
            ],
            horarios: ['08:00', '08:30', '09:00', '09:30', '10:00', '12:00', '13:00', '13:30', '14:30', '15:00', '15:30', '16:00', '16:30', '18:00'],
            nameDono: '',
            namePet: '',
            data: '',
            servico: '',
            horario: ''
        }
    },

    methods: {
        submitFromWhatsapp() {
            const phoneNumber = '32999046481';
            const message = encodeURIComponent(
                `Nome do Dono: ${this.nameDono}\nNome do Pet: ${this.namePet}\nData Desejada: ${this.data}\nHorário Desejado: ${this.horario}\nServiço Desejado: ${this.servico}`
            );

            const whatsappLink = `https://wa.me/${phoneNumber}?text=${message}`;

            window.open(whatsappLink, '_blank');
        },
    }
}

</script>

<style scoped land="scss">
.container-contacts {
    @apply w-full flex justify-center items-center py-24;
    background-image: url('../assets/pexels-goochie-poochie-grooming-19145878.jpg');
    /* Caminho para a sua imagem de fundo */
    background-size: cover;
    /* Ajusta o tamanho da imagem para cobrir toda a div */
    background-position: center;
}

.container-form {
    @apply w-[90%] md:w-[80%] px-10 py-10 flex flex-col md:flex-row gap-24 rounded-xl;
    @apply backdrop-filter backdrop-blur-sm bg-opacity-30 bg-black;
    /* Ajuste conforme necessário */
}

.input-label {
  @apply text-blue-800 font-bold mb-1;
}

.input-field {
  @apply px-4 py-2 w-full rounded bg-gray-200 text-gray-800 outline-none focus:border-slate-300;
}

.btn-agendar {
    @apply bg-green-500 hover:bg-green-700 text-white font-bold px-6 py-2;
}
</style>