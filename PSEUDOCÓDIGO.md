# projetobackend
Projeto do curso de ADS da Uninter  - Stefany Gabrielle de Oliveira RU 4325405
Pseudocódigo para representação

Início

Definir estrutura Usuario:
    - id
    - nome
    - email
    - senha_hash
    - tipo (administrador, médico, recepcionista)

Definir estrutura Paciente:
    - id
    - nome
    - data_nascimento
    - cpf
    - endereco
    - telefone
    - historico_medico

Definir estrutura Consulta:
    - id
    - paciente_id
    - profissional_id
    - data
    - tipo (presencial, telemedicina)
    - observacoes

Função autenticar_usuario(email, senha):
    Buscar usuário por email
    Se usuário existir E senha_hash for válida:
        Retornar token de sessão
    Senão:
        Retornar "acesso negado"

Função cadastrar_paciente(paciente):
    Validar CPF
    Verificar se já existe paciente com mesmo CPF
    Se não existir:
        Salvar paciente
        Registrar log de criação
    Senão:
        Retornar "Paciente já cadastrado"

Função atualizar_prontuario(paciente_id, novo_historico):
    Buscar paciente pelo ID
    Se encontrado:
        Atualizar campo historico_medico
        Registrar log de alteração
    Senão:
        Retornar "Paciente não encontrado"

Função registrar_consulta(consulta):
    Verificar se paciente e profissional existem
    Validar data e tipo de consulta
    Salvar consulta
    Retornar "Consulta registrada com sucesso"

Função listar_pacientes():
    Retornar lista de pacientes cadastrados

Função registrar_log(acao, usuario, dados):
    Salvar log de auditoria com timestamp

Fim

