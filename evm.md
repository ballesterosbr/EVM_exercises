# EVM
---
[Yellowpaper Ethereum:](https://ethereum.github.io/yellowpaper/paper.pdf)

---

## Tools

Es necesario tener Go instalado y configurar las rutas GOPATH y GOBIN:
https://github.com/golang/go/wiki/SettingGOPATH

Instalación de las herramientas utilizadas para la demo:

```

go get github.com/ebuchman/evm-tools/...

cd $GOPATH/src/github.com/ebuchman/evm-tools
git pull origin master
go install disasm evm
```
https://github.com/CoinCulture/evm-tools/blob/master/analysis/guide.md#execution

---

### 00s
```$ evm --debug --codefile 00s run```
### 10s
```$ evm --debug --codefile 10s run```
### 20s
```$ evm --debug --codefile 20s run```
### 40s & 50s
```$ evm --debug --codefile 40_&_50 run```
### f0s
```$ evm --debug --codefile f0s run```

## Demos

### Demo 1
```$ evm --debug --codefile add1```

### Demo 2
```$ evm --debug --codefile add2```

### Demo 3 - Operaciones encadenadas
```$ evm --debug --codefile ops3 --input 000000000000000000000000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000000010000 run```

### Demo 4 - Loop (No eficiente vs Eficiente)
```$ evm --debug --codefile testloop --input 0000000000000000000000000000000000000000000000000000000000000003 run```

```$ evm --debug --codefile testloop2 --input 0000000000000000000000000000000000000000000000000000000000000003 run```

### Demo 5 - Shift 
```$ evm --debug --codefile shift --input 03 run```

```$ evm --debug --codefile shift2 --input 123456 run```

### Demo 6 - Memory
```$ evm --debug --codefile memory run```

```$ evm --debug --codefile mstore run```

### Demo 7 - Storage
```$ evm --debug --codefile store --input 4C48053ccbA2B109CCDd7CDDc80f6d6ae60832E2 run```

### Demo 8 - Excepciones

#### Out of gas
```$ evm --debug --gas 8 --codefile oog run```

#### Invalid Opcode
```$ evm --debug --codefile iop run```

#### Invalid Jump Destination
```$ evm --debug --codefile ijd --input 0000000000000000000000000000000000000000000000000000000000000002 run```

#### Stack underflow
```$ evm --debug --codefile stu run```

### Demo 9 - Smart contract
```$ solc --hashesh SafeMath.sol```

```$ evm --debug --codefile contract --input c8a4ac9c00000000000000000000000000000000000000000000000000000000000000050000000000000000000000000000000000000000000000000000000000000004 run```