# Laboratórios de Serviços de Rede - Linux Debian 13

## 📌 Sobre o projeto

<img width="1280" height="720" alt="Laboratórios de Serviços de Rede -   Linux Debian 10 _ Videoaula 01 - Introdução 2-19 screenshot" src="https://github.com/user-attachments/assets/4057c0ca-fd48-4756-8194-ade9115fb010" />


Este projeto tem como objetivo documentar a implementação de um laboratório virtual de serviços de rede, utilizando Linux como base para a infraestrutura de servidores, com integração de serviços de rede, gerenciamento de domínio, resolução de nomes e estações clientes Windows.

O ambiente foi planejado para simular uma infraestrutura corporativa, permitindo estudar a comunicação entre servidores e clientes, a administração de redes e os principais serviços utilizados em ambientes empresariais.

## 🎯 Objetivos

- Estudar a administração de servidores Linux.
- Compreender a arquitetura de uma rede corporativa.
- Planejar e implementar serviços de DNS.
- Estudar o gerenciamento de domínio com Active Directory.
- Compreender a função de firewall, DHCP e proxy.
- Integrar servidores Linux e Windows.
- Documentar a infraestrutura e suas configurações técnicas.

## 🏗️ Arquitetura do laboratório

A topologia proposta contém uma rede interna conectada à rede externa por meio de um servidor responsável pelos serviços de infraestrutura e controle de tráfego.

### Componentes da infraestrutura

| Componente | Endereço IPv4 | Função prevista |
|---|---|---|
| Firewall / DHCP / Proxy | `192.168.X.X` (interface externa) | Controle de tráfego e serviços de rede |
| Firewall / DHCP / Proxy | `172.16.1.1` (interface interna) | Gateway da rede interna |
| DNS Master | `172.16.1.2` | Resolução de nomes e gerenciamento da zona DNS |
| DNS Slave | `172.16.1.3` | DNS secundário e redundância |
| Web / DB | `172.16.1.4` | Hospedagem web e serviços de banco de dados |
| AD/DC Master | `172.16.1.5` | Controlador de domínio principal |
| AD/DC Slave | `172.16.1.6` | Controlador de domínio secundário |
| Cliente Windows | `172.16.1.100` | Estação cliente |
| Cliente Windows | `172.16.1.101` | Estação cliente |

**Domínio previsto:** `empresax.com.br`

**Rede interna IPv4:** `172.16.1.0/24` (considerando a máscara `/24` como referência para o endereçamento ilustrado).

> **Observação:** os endereços apresentados representam o planejamento da topologia. A interface externa, o endereçamento IPv6, as máscaras e as configurações efetivamente aplicadas deverão ser confirmados durante a implementação.

## 🖥️ Servidores e serviços

### 1. Firewall, DHCP e Proxy

Servidor responsável pela comunicação entre a rede interna e a externa.

Funções previstas:
- Filtragem e controle do tráfego de rede.
- Encaminhamento de pacotes entre interfaces.
- Distribuição automática de endereços IP, conforme a configuração DHCP.
- Intermediação de conexões por meio de proxy, conforme os requisitos do ambiente.

### 2. DNS Master

Servidor DNS primário responsável por manter as informações da zona DNS do domínio.

Atividades previstas:
- Configuração da zona `empresax.com.br`.
- Criação de registros para os servidores e serviços internos.
- Resolução de nomes para endereços IP.
- Validação das consultas DNS.

### 3. DNS Slave

Servidor DNS secundário destinado a manter uma cópia da zona DNS primária, conforme a configuração de transferência de zonas.

Objetivos:
- Estudar a replicação de zonas DNS.
- Compreender a redundância do serviço.
- Validar a resolução de nomes utilizando o servidor secundário.

### 4. Servidor Web / Banco de Dados

Servidor destinado à hospedagem de aplicações web e serviços de banco de dados.

Os softwares, as versões e as configurações específicas serão documentados de acordo com a implementação realizada.

### 5. Active Directory: controlador Master

Servidor Windows destinado ao gerenciamento centralizado do domínio.

Funções previstas:
- Administração de usuários e grupos.
- Autenticação centralizada.
- Gerenciamento de computadores do domínio.
- Aplicação de políticas de grupo, conforme a configuração adotada.
- Integração com o DNS.

### 6. Active Directory: controlador Slave

Segundo controlador de domínio, destinado a complementar o serviço de diretório e proporcionar redundância, conforme a configuração de replicação implementada.

### 7. Clientes Windows

Duas estações clientes destinadas a testar a comunicação com os servidores e a integração com o domínio corporativo.

Testes previstos:
- Conectividade com o gateway.
- Resolução de nomes internos.
- Comunicação com os controladores de domínio.
- Ingresso no domínio, quando configurado.
- Autenticação e acesso aos serviços disponibilizados.

## 🌐 Endereçamento IPv6

A topologia também apresenta endereços IPv6 para a interface interna e para os servidores.

O prefixo ilustrado é `2001:db8:acad:cafe::/64`, reservado para documentação e exemplos. Ele não deve ser utilizado como prefixo público real em uma implantação de produção.

Os endereços IPv6 definitivos e os testes de conectividade serão registrados conforme a implementação do laboratório.

## 🔬 Metodologia de documentação

Cada etapa do laboratório deve registrar somente as atividades efetivamente executadas, incluindo:

- Configurações aplicadas.
- Comandos utilizados.
- Arquivos de configuração modificados.
- Resultados dos testes realizados.
- Evidências relevantes.
- Problemas encontrados e respectivas soluções.

Essa abordagem permite reproduzir o ambiente, revisar as configurações e utilizar o repositório como material de estudo e portfólio técnico.

## 🛠️ Ambiente de virtualização

O laboratório utiliza máquinas virtuais para simular os componentes de uma infraestrutura corporativa.

A plataforma de virtualização, os sistemas operacionais, as versões dos serviços e os recursos alocados a cada máquina devem ser registrados conforme o ambiente efetivamente utilizado.

## 📚 Conhecimentos abordados

- Administração Linux.
- Serviços de rede.
- DNS e resolução de nomes.
- DHCP e endereçamento IP.
- Firewall e controle de tráfego.
- Proxy de rede.
- Windows Server e Active Directory.
- Integração entre Linux e Windows.
- IPv4 e IPv6.
- Virtualização e infraestrutura de TI.
- Documentação técnica.

## ⚠️ Aviso

Este repositório tem finalidade educacional. A topologia representa um ambiente de laboratório e não deve ser considerada uma configuração pronta para produção. Qualquer implantação real exige validação de segurança, planejamento de endereçamento, controle de acesso, monitoramento e procedimentos de recuperação.

---

**Projeto:** Laboratório de Serviços de Rede  
**Finalidade:** Estudo prático de infraestrutura, administração de servidores e serviços de rede.
