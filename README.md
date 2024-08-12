# Password-Manager-com-dicion-rio-sendo-o-Banco-de-Dados
Password Manager com dicionário sendo o Banco de Dados

- O desafio é criar um gerenciador de senhas
- O programa deve perguntar para o usuário se ele quer cadastrar uma senha nova ou pegar uma senha existente. Independente da operação ele deve usar uma senha mestre: "uh&g7fnsd8" para aprovar qualquer consulta/edição no sistema. Se o usuário quiser adicionar uma senha, deve pedir qual o nome do sistema de onde essa senha faz parte, qual o login e qual a senha a ser cadastrada. Se for para consultar, seu programa deve exibir os nomes dos sistemas disponíveis e o usuário pode escolher qual senha quer pedir e seu programa deve dar para ela a resposta de login e senha. Se quiser que as suas senhas cadastradas possam ser usadas para consulta, coloque tudo em um loop infinito e dê algum comando para o usuário conseguir finalizar o processo

  gerenciador_senhas = {
    "Gmail": ("lira@emailfalso.com", "minhasenha123"),
    "Github": ("pythonimpressionador", "senhadoida"),
    "Cartão de Crédito": ("NumeroFalsodoCartao", "123456"),
    "Portal Hashtag": ("usuario@gmail.com", "123456")
}

senha_banco = input("Digite a senha mestre para acessar o banco")
if senha_banco != "uh&g7fnsd8":
    print("Senha incorreta, acesso negado.")
else:
    acao = input("O que você deseja fazer? Cadastrar (digite 1) ou Consultar uma senha (digite 2). Deixe em branco para finalizar")
    while acao != "":
        if acao == "1":
            nome_sistema = input("Digite o nome do sistema a ser cadastrado")
            login = input("Digite o login")
            senha = input("Digite a senha")
            gerenciador_senhas[nome_sistema] = (login, senha)
            print(f"Senha salva com sucesso. {nome_sistema}: {gerenciador_senhas[nome_sistema]}")
        elif acao == "2":
            nomes_sistemas = list(gerenciador_senhas.keys())
            texto_nomes_sistemas = "\n".join(gerenciador_senhas)
            print("Sistemas disponíveis:")
            print(texto_nomes_sistemas)
            sistema = input("Escolha o sistema que quer consultar a senha. Digite o nome exatamente como aparece acima.")
            usuario, senha = gerenciador_senhas[sistema]
            print("Usuário {}".format(usuario))
            print("Senha {}".format(senha))
        else:
            break
        acao = input("O que você deseja fazer? Cadastrar (digite 1) ou Consultar uma senha (digite 2). Deixe em branco para finalizar")
        
