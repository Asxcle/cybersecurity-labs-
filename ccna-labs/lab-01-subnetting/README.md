#Lab 01 - Configuração de Roteamento Básico

## Objetivos
- Configurar endereçamento IP em end systems e roteador
- Verificar conectividade com ping

## Topologia

![Topologia da Rede](topologia-basica.png)

**Descrição**
- 1 Roteador (R1)
- 1 PC (PC0)
- Rede base: 192.168.1.0/24

## Configurações

### Router 1(R1)
```cisco
enable
configure terminal

! Interface conectada à rede
interface GigabitEhernet0/0
  ip address 192.168.1.1 255.255.255.0
  no shutdow
  exit

**Resuldado esperado:**
```
       192.168.1.0/24 is variably subnetted, 2 subnets, 2 maks
C      192.168.1.0/24 is direclty connected, GigabitEthernet0/0
L      192.168.1.1/32 is directly connected, GigabitEthernet0/0
```
### Testar conectividade

```
PC1 (192.168.1.2) > ping 192.168.1.1 (roteador)
```

**Resultado esperado: **
```

Reply from 192.168.1.1: bytes=32 time<1ms TTL=255
Reply from 192.168.1.1: bytes=32 time<1ms TTL=255
Reply from 192.168.1.1: bytes=32 time<1ms TTL=255
Reply from 192.168.1.1: bytes=32 time<1ms TTL=255

Ping statistics for 192.168.1.1:
	Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
	Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

### Traceroute para verificar caminho
```
PC1> tracert 192.168.1
```

**Resultado esperado:**
```
Tracing route to 192.168.1.1:
1	0ms	0ms	0ms	192.168.1.1
```

## Conceitos Aprendidos
- Configuração de interfaces em roteadores Cisco
- Rotas entre roteadores
- Verificação de conectividade (ping, traceroute)

##Informações do Lab
- **Data de criação:**30/11/2025
- **Tempo estimado:** 10-20 minutos
- **Dificuldade:** Iniciante
- **Ferramentas:** Cisco Packet Tracer 8.2
- **Autor:** Ana Raquel
