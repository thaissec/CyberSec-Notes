# Componentes de rede e endereçamento IP

## Componentes

| Componente | Função | Analogia |
|---|---|---|
| **Switch** | Conecta dispositivos na mesma rede local | A tomada da rede |
| **Roteador** | Conecta redes diferentes | A avenida entre bairros |
| **Firewall** | Permite ou bloqueia tráfego por regra | O portão do condomínio |
| **Servidor** | Serve sites, arquivos, e-mails, bancos de dados | A loja |
| **Cliente** | Consome os recursos | O cliente da loja |

## IP privado e IP público

| | Privado | Público |
|---|---|---|
| Uso | Rede local | Visível mundialmente |
| Quem atribui | Seu roteador | Seu provedor |
| Faixas | `192.168.x.x`, `10.x.x.x`, `172.16 a 31.x.x` | O resto |

Ao acessar o Google, o servidor vê o **IP público do roteador**, não o IP privado do seu notebook.

## Sub-redes e máscara

O IP tem parte de **rede** e parte de **host**. A máscara diz onde termina uma e começa a outra. `/24` significa 24 bits de rede e 8 de host.

| Notação | Máscara | Endereços | Utilizáveis | Uso típico |
|---|---|---|---|---|
| `/8` | 255.0.0.0 | 16.777.216 | 16.777.214 | Redes muito grandes |
| `/16` | 255.255.0.0 | 65.536 | 65.534 | Redes corporativas grandes |
| `/24` | 255.255.255.0 | 256 | 254 | Casa e escritório (`192.168.1.0/24`) |
| `/30` | 255.255.255.252 | 4 | 2 | Ligação entre dois roteadores |

O primeiro endereço (`.0`) identifica a rede e o último (`.255`) é o broadcast.

## Gateway, DHCP e NAT

- **Gateway:** roteador da rede local (ex.: `192.168.1.1`). Destino em outra rede? O pacote vai ao gateway.
- **DHCP:** entrega IP, máscara, gateway e DNS automaticamente. Etapas **DORA**: Discover, Offer, Request, Acknowledge.
- **NAT:** vários dispositivos com IP privado saem para a internet com um único IP público. O roteador guarda uma tabela de conexões.

## MAC e IP

- **MAC:** endereço físico da placa, usado dentro da rede local; muda a cada salto.
- **IP:** endereço lógico, vale de ponta a ponta.
