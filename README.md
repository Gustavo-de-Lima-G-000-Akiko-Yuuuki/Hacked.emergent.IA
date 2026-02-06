# Hacked.emergent.IA
Basicamente gostei dessa IA de criação de site interface etc tem um custo de credito mas pode ser "hackeado"https://app.emergent.sh/chat
Para baixar exatamente essa estrutura que você listou, vamos criar um arquivo compactado e usar o link do servidor que já sabemos que funciona.

Siga estes passos:
### 0. Crie seu app normalmente, chegou no resultado que gostou e quer os arquivos completos siga esses passos:

### 1. Pare o servidor atual
No terminal, aperte **`Ctrl + C`**.

### 2. Crie o arquivo ZIP da pasta `/app`
Execute este comando para compactar tudo o que você listou acima:
```bash
zip -r /root/projeto_completo.zip /app
```
*Este comando vai incluir o backend, frontend, memory, testes e os arquivos ocultos (como o `.emergent`).*

### 3. Inicie o servidor Python novamente
```bash
cd /root
python3 -m http.server 9000
```

### 4. Acesse o link para baixar
Clique no link abaixo no seu navegador:

👉 **[https://vscode-61af4420-1c16-4dca-8793-0eab368159d1.preview.emergentagent.com/proxy/9000/](https://vscode-61af4420-1c16-4dca-8793-0eab368159d1.preview.emergentagent.com/proxy/9000/)**

### 5. O que fazer na página:
1.  Procure pelo arquivo **`projeto_completo.zip`**.
2.  Clique nele para baixar.

---

### Por que o seu `zip` anterior deu aviso?
Na lista que você mandou, existem pastas como `.ruff_cache` e `.emergent`. Às vezes, esses arquivos de sistema ou cache estão sendo usados pelo editor enquanto você tenta zipar. O comando `zip -r` que passei acima vai ignorar os erros menores e criar o arquivo mesmo assim.

**Dica:** Se o download demorar muito (devido aos 1.3GB), verifique se você realmente precisa da pasta `.ruff_cache`. Se quiser um arquivo **menor e mais rápido**, você pode ignorar as pastas de cache com este comando:
```bash
zip -r /root/projeto_completo.zip /app -x "*/.ruff_cache/*" "*/.emergent/*"
```
Isso tornará o arquivo bem mais leve para baixar!


Para acessar a pasta **root** (onde está o seu arquivo `.zip`) em vez da pasta **app**, você precisa parar o servidor e iniciá-lo dentro da pasta `/root`.

Siga estes passos:

### 1. Pare o servidor atual
No terminal, aperte:
**`Ctrl + C`**

### 2. Vá para a pasta root
Digite o comando:
```bash
cd /root
```

### 3. Inicie o servidor novamente
Agora sim, inicie o servidor dentro de `/root`:
```bash
python3 -m http.server 9000
```

### 4. Acesse o link
Abra o mesmo link de antes no seu navegador:

👉 **[https://vscode-61af4420-1c16-4dca-8793-0eab368159d1.preview.emergentagent.com/proxy/9000/](https://vscode-61af4420-1c16-4dca-8793-0eab368159d1.preview.emergentagent.com/proxy/9000/)**

---

### O que mudou?
Como você deu o comando `cd /root` antes de iniciar o Python, agora quando você abrir o link, ele vai listar os arquivos que estão em `/root` (como o `projeto.zip` ou `projeto_completo.zip`) em vez dos arquivos da pasta `/app`.

**Dica rápida:** Se você quiser servir a pasta `/root` sem precisar sair da pasta `/app`, você pode usar este comando direto (funciona no Python 3.7+):
```bash
python3 -m http.server 9000 --directory /root
```
