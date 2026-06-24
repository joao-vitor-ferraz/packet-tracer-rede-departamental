# Cisco Packet Tracer — Rede Departamental

Este repositório contém um projeto desenvolvido no **Cisco Packet Tracer** para a unidade curricular de **Comunicação de Dados**, no curso de **Redes e Segurança Informática**.

O objetivo do trabalho foi implementar uma infraestrutura de rede para uma organização com três departamentos: **Financeiro**, **Administrativo** e **Comercial**. A solução inclui endereçamento IPv4 com VLSM, encaminhamento dinâmico, serviços de rede e políticas básicas de segurança com ACLs.

## Topologia da rede

A infraestrutura foi organizada com um **Router Principal**, responsável pela interligação dos três routers departamentais e da rede externa. Cada departamento possui a sua própria rede local, com switch, hosts e gateway próprio.

Departamentos implementados:

* Departamento Financeiro
* Departamento Administrativo
* Departamento Comercial

Também foram adicionados:

* Servidor externo para DNS e HTTP
* Servidor Comercial para DHCP do Departamento Comercial
* Access points nos departamentos Financeiro e Administrativo
* Impressora de rede no Departamento Comercial

## Endereçamento lógico

O endereço base da rede interna foi calculado a partir dos números dos alunos:

* 34296 → 3 + 4 + 2 + 9 + 6 = 24
* 36327 → 3 + 6 + 3 + 2 + 7 = 21
* 24 + 21 = 45

Assim, a rede base utilizada foi:

```text
192.168.45.0/24
```

## Redes utilizadas

| Rede                                     | Endereço          |
| ---------------------------------------- | ----------------- |
| Financeiro                               | 192.168.45.0/26   |
| Comercial                                | 192.168.45.64/27  |
| Administrativo                           | 192.168.45.96/28  |
| Ligação R-Comercial ↔ Servidor Comercial | 192.168.45.112/30 |
| Servidor externo                         | 100.200.10.0/24   |

## Serviços configurados

* DHCP no Router Financeiro
* DHCP no Router Administrativo
* DHCP no Servidor Comercial
* DNS no servidor externo
* HTTP no servidor externo
* OSPF entre routers
* ACLs para controlo de tráfego
* Rede wireless nos departamentos Financeiro e Administrativo

## Encaminhamento

Foi utilizado **OSPF em área 0** para permitir a troca dinâmica de rotas entre os routers da infraestrutura.

Routers configurados:

* R-PRINCIPAL
* R-FINANCEIRO
* R-ADMINISTRATIVO
* R-COMERCIAL

## Segurança

Foram configuradas ACLs para:

* Restringir o acesso livre do Departamento Comercial ao Departamento Financeiro
* Controlar o acesso dos departamentos à rede externa
* Permitir os serviços necessários, como DHCP, ICMP, DNS e HTTP

## Ficheiros do repositório

| Ficheiro                    | Descrição                                |
| --------------------------- | ---------------------------------------- |
| `Relatório.pdf`             | Relatório final do projeto               |
| `planta.pkt`                | Ficheiro do Cisco Packet Tracer          |
| `Comandos_Dispositivos.zip` | Comandos CLI organizados por dispositivo |

## Tecnologias utilizadas

* Cisco Packet Tracer
* IPv4
* VLSM
* DHCP
* DNS
* HTTP
* OSPF
* ACLs
* Wireless
* Switching e routing Cisco

## Autores

* João Vitor Ferraz
* João Gabriel Primo

## Nota

Este projeto foi desenvolvido com fins académicos, no contexto da unidade curricular de Comunicação de Dados.
