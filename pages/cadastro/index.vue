<script setup lang="ts">

import Simple from "~/components/form/simple.vue";
import Select from "~/components/inputs/select.vue";
import Text from "~/components/inputs/text.vue";
import {da} from "cronstrue/dist/i18n/locales/da";
import Button from "~/components/inputs/button.vue";

const options = [
    'Selecione',
    'Masculino',
    'Feminino',
    'Outro'
]

const steps = [
    'Dados Pessoais',
    'Endereço',
    'Responsáveis',
    'Cursos e Pagamentos'
]

const data = reactive({
    cpf: '',
    nome_aluno: '',
    nome_social: '',
    nome_pai: '',
    nome_mae: '',
    telefone: '',
    email: '',
    nacionalidade: '',
    sexo: '',
    cidade_nascimento: '',
    estado_nascimento: '',
    data_nascimento: '',
    etnia: '',
    estado_civil: '',
    origem_cadastro: '',
    aluno_indicacao: '',
    necessidades_especiais: ''

})

</script>
<template>
    <div class="container">

        <h1>Formulário de Inscrição</h1>
        <steps-step-circle :steps="steps" />
        <hr />
        <Simple>
            <div class="dados-pessoais">

                <Text
                    label="CPF:"
                    width="120px"
                    placeholder="XXX.XXX.XXX-XX"
                    v-model="data.cpf"
                />
                <Text
                    label="Nome do Aluno:"
                    width="300px"
                    v-model="data.nome_aluno"
                />
                <Text
                    label="Nome Social:"
                    width="300px"
                    v-model="data.nome_social"
                />
                <Text
                    label="Telefone:"
                    width="160px"
                    placeholder="(99) 99 9 9999 9999"
                    v-model="data.telefone"
                />
                <Text
                    label="Email:"
                    width="200px"
                    placeholder="fulano@example.com"
                    v-model="data.email"
                />

                <Select
                    label="Nacionalidade:"
                    :options width="160px"
                    v-model="data.nacionalidade"
                />
                <Select
                    label="Sexo:"
                    :options
                    width="160px"
                    v-model="data.sexo"
                />

                <Text
                    label="Cidade de Nascimento:"
                    width="300px"
                    v-model="data.cidade_nascimento"
                />

                <Select
                    label="Estado de Nascimento:"
                    width="160px"
                    v-model="data.estado_nascimento"
                />

                <Text
                    label="Data de Nascimento"
                    type="date"
                    width="140px"
                    v-model="data.data_nascimento"
                />

                <Select
                    label="Etnia:"
                    width="140px"
                    v-model="data.etnia"
                />

                <Text
                    label="Necessidades Especiais:"
                    width="340px"
                    v-model="data.necessidades_especiais"
                />
                <Text
                    label="Nome da Mãe:"
                    width="300px"
                    v-model="data.nome_mae"
                />
                <Text
                    label="Nome do Pai:"
                    width="320px"
                    v-model="data.nome_pai"
                />
                <Select
                    label="Estado Civil:"
                    width="140px"
                    v-model="data.estado_civil"
                />
                <Text
                    label="Origem de Cadastro:"
                    width="340px"
                    v-model="data.origem_cadastro"
                />
                <Text
                    label="Indicado pelo Aluno:"
                    width="300px"
                    v-model="data.aluno_indicacao"
                />
            </div>
            <div class="footer">
                <Button
                    value="Anterior"
                />
                <Button
                    value="Proximo"
                />
            </div>
        </Simple>
    </div>
</template>

<style scoped lang="scss">
.container{
    max-width: 1280px;
    margin: 20px auto;
    padding: 0 40px;

    h1 {
        text-align: center;
        margin-bottom: 20px;
    }
}

.dados-pessoais {
    margin: 20px;
    display: flex;
    gap: 20px;
    width: 100%;
    align-items: center;
    flex-wrap: wrap;

}

.footer {
    display: flex;
    justify-content: space-between;
}
</style>