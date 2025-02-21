# Gerador de QR Code para Pagamentos Pix

Este projeto é um gerador de QR Code para pagamentos via Pix, desenvolvido em Python. Ele cria uma string no formato esperado pelo Banco Central do Brasil e gera um QR Code correspondente.

## 🚀 Funcionalidades
- Geração de **códigos Pix** no formato correto
- Cálculo do **CRC16** para validação
- Criação de **QR Code** a partir do código gerado
- Salvamento do QR Code como uma imagem

## 📌 Tecnologias Utilizadas
- Python 3
- [crcmod](https://pypi.org/project/crcmod/) (para calcular o CRC16)
- [qrcode](https://pypi.org/project/qrcode/) (para gerar QR Codes)
- [Pillow (PIL)](https://pypi.org/project/Pillow/) (para manipulação de imagens)

## 📥 Instalação
### 1️⃣ Clone o repositório
```sh
git clone https://github.com/Kethelynl/API_PIX.git
cd API_PIX
```

### 2️⃣ Instale as dependências
```sh
pip install -r requirements.txt
```
Se o arquivo `requirements.txt` não existir, instale os pacotes manualmente:
```sh
pip install crcmod qrcode[pil] Pillow
```

## 🔧 Como Usar
No arquivo `pixqrcode.py`, crie uma instância da classe `Payload` e gere o QR Code:

```python
from pixqrcode import Payload

pix = Payload(
    nome="Nome Sobrenome",
    chavepix="12345678900",
    valor="1.00",
    cidade="Cidade Ficticia",
    txtId="LOJA01"
)
pix.gerarPayload()
pix.gerarQrcode(pix.payload_completa)
```
Isso irá gerar um QR Code e salvá-lo como `pixqrcode.png`.

## 📸 Exemplo de QR Code Gerado
![QR Code Pix](pixqrcode.png)

## 🛠 Possíveis Problemas e Soluções
### 1️⃣ Módulo `PIL` não encontrado
**Erro:** `ModuleNotFoundError: No module named 'PIL'`

**Solução:** Instale o pacote Pillow:
```sh
pip install Pillow
```

### 2️⃣ Erro ao enviar para o GitHub
Se o erro `failed to push some refs to ...` aparecer, tente atualizar o repositório local antes de fazer o `push`:
```sh
git pull origin main --rebase
git push origin main
```

## 📄 Licença
Este projeto está sob a licença MIT. Sinta-se à vontade para contribuir! 🚀

