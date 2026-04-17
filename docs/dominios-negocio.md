# Domínios de Negócio

## Visão Geral

A solução foi organizada considerando separação de responsabilidades de negócio, facilitando evolução funcional, manutenção e entendimento do sistema.

---

## Domínio de Lançamentos Financeiros

Responsável pelo registro das movimentações financeiras realizadas pelo comerciante.

### Principais responsabilidades

- Registrar créditos e débitos.
- Validar dados informados.
- Consultar lançamentos realizados.
- Garantir persistência segura das operações.
- Publicar eventos para demais componentes.

---

## Domínio de Consolidação Diária

Responsável pelo cálculo e disponibilização do saldo consolidado por data.

### Principais responsabilidades

- Consumir eventos financeiros.
- Processar movimentações recebidas.
- Calcular saldo diário.
- Disponibilizar consulta consolidada.
- Permitir reprocessamento quando necessário.

---

## Domínio de Segurança e Acesso

Responsável pelo controle de autenticação e autorização.

### Principais responsabilidades

- Validar identidade do usuário.
- Gerenciar permissões.
- Proteger acessos indevidos.
- Registrar trilhas de auditoria.

---

## Domínio Operacional

Responsável pela sustentação técnica da plataforma.

### Principais responsabilidades

- Monitoramento dos serviços.
- Gestão de logs e alertas.
- Acompanhamento de performance.
- Apoio ao troubleshooting.

---

## Benefícios da Separação por Domínio

- Redução de acoplamento.
- Evolução independente das capacidades.
- Melhor entendimento do negócio.
- Maior escalabilidade organizacional e técnica.

---

## Resultado Esperado

Uma solução alinhada ao negócio, com responsabilidades claras e preparada para crescimento futuro.
