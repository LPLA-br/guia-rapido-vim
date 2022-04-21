##Sobre

pt-BR
Um manual de consulta rápida e prática para iniciantes
do vim. Imprima-o ou Matenha-o em uma janela resevada
para consultas breves.
Obrigado por ler-lo, tenha um dia bom e produtivo.

#Autor

Escrito por: Luiz Paulo de Lima Araújo
Email:**anonimus**

##Legenda
```
número - Neste documento indica que e possível digitar um
 	 número antes da combinação de teclas a ser feita
	 alterando a ação desejada em quantidade.
	 exemplo;	10g vai para linha 10
	 		g vai para a linha final do texto

**Registradores** - registros que armazenam informação textual.
 somente leitura
	: último comando
	. último texto que você inseriu
	% nome do arquivo corrente
	# nome do arquivo editado anteriormente
 leitura e escrita
	" registrador padrão para onde vai deleção, cópia implícita
	0 auxiliar do registrador acima
	1 até 9	fila de deleção, conteúdo mais recente fica em 1 e mais antigo fica em 9
	- auxiliar dos registradores numéricos, evitando o rápido enchimento. deleção
	  vem para aqui
	a até z e A até Z registradores de uso geral para você usar
	+ clipboard do sistema
	- registrador buraco negro
	/ registrador de última busca

**buffers** - vários textos abertos sem ser em tela dividida
	Digamos que você ,no terminal, abriu vários textos com o vim assim:
		vim a.txt b.txt c.txt
	Se deparando com apenas um texto na tela principal do editor.
	use os comandos :bn :bp :bd :ls para lidar com estes buffers.
```
##Uso básico

#Modo Inserção i
```
	del		apaga letra abaixo do cursor.
	ctrl shift v	colar texto do clipboard do sitema para o vim. Ou shift insert.

	ctrl p 		autocompleta com palavras pre-existentes no texto de forma interativa.

	ctrl t		isere tabulação no início da linha.
	ctrl d		apaga tabulação no início da linha.
      0 ctrl d		apaga todas as tabulações da linha.

	ctrl e		recria a letra abaixo do cursor para a linha atual.
	ctrl y		recria a letra acima  do cursor para a linha atual.

	ctrl c		voltar para o modo normal.
	ctrl a		iserir trecho previamente salvo.		

	ctrl r R	colar conteúdo do registrador, onde R é o nome do registrador.

	ctrl u 		apagar todo o conteúdo de onde o cursor está até o início da linha.
	ctrl w		apagar palavra antes do cursor.

	ctrl n 		autocompleta com palavras pre-existentes.
```
#Modo Visual v
```
	o		cria linha vazia abaixo, vai para, entra em insert.
	O		cria linha vazia acima, vai para, entra em insert.

	U		mudar área selecionada para maiúscula(caixa-alta).
	u		mudar área selecionada para minúscula(caixa-baixa).

  número>		adicionar mais 1 ou N tabulações para área selecionada.
  número<		adicionar menos 1 ou N tabulações para área selecionada.

	c		apaga área selecionada e vai para o modo INSERT (c change).
	d		apaga área selecionada e vai para o modo NORMAL (d delete).
	y		copia área selecionada e vai para o modo NORMAL (y yank).
```
#Modo Normal esc
```
	o 		cria linha vazia abaixo, vai para, e entra em insert
	O 		cria linha vazia acima , vai para, e entra em insert

	ctrl r		refazer
	u		desfazer
	p		colar conteúdo previamente copiado ou cortado (p paste).

  númeroyy		copiar linha inteira onde o cursor está (y yank).
  númerodd		recorta a linha inteira onde o cursor está (d delete).

  númerodw		apagar palavra para frente (dw delete word).
  númerox		apagar letras a frente do cursor.

  númerod$		apagar do cursor até o fim da linha.
  númerod0		apagar do cursor até o comesso da linha.
	

	qq		comessar ou parar de gravar um MACRO.
	@q		colar MACRO gravada.

	/texto		localizar um padrão de cima para baixo.
	?texto		localizar um padrão de baixo para cima.
  númeron		mostra o proximo padrão encontrado.

  númerog		ir para linha especificada por número. g sem número vai para o fim arquivo.

  númerow		mover cursor para frente pelo comesso das palavras.
  númeroe		mover cursor para frente pelo fim das palavras.
  númerob		mover cursor para traz pelo comesso das palavras.	

  número$		mover cursor para o fim da linha.
  número0		mover cursor para o comesso da linha.

  número}		mover cursor para o parágrafo abaixo.		
  número{		mover cursor para o parágrafo acima.

  númeroj		mover cursor para baixo.
  númerok		mover cursor para cima.

	mx		marcar atual posição do cursor.
	'x		saltar para última posição marcada.
	''		voltar para linha que o cursor estava antes do salto.
	'.		saltar para última linha modificada por você.
	
	ctrl y		rolar texo uma linha para cima.
	ctrl e		rolar texo uma linha para baixo.

	H		mover cursor para o topo da tela.
	M		mover cursor para o meio da tela.
	L		mover cursor para o fim da tela.

	ctrl ww		mudar foco da tela dividida.
	ctrl wv		divide o texto atual em duas janelas verticais.
	ctrl ws		dividir texto atual em duas janelas horizontais.
	ctrl w+		aumentar altura da janela onde se encontra o cursor.
	ctrl w-		diminuir altura da janela onde se encontra o cursor.
	ctrl w<		diminuir largura da janela onde se encontra o cursor.
	ctrl w>		aumentar largura da janela onde se encontra o cursor.
	ctrl w=		fazer todas as janelas terem a mesma largura e altura.
	ctrl wr		rotacionar janelas.
	ctrl wq		fechar janela em que o cursor se encotra.

	"AB		gravar registrador de textos onde A é o nome do
			registrador e B é a operação a ser feita (p-paste
			y-yank d-delete c-change)
```
#Linha De Comando :
```
	:help	COMANDO		obter ajuda acerca de um comando.

	:e /file		abrir um arquivo do diretório especificado.
	:w			salvar no dirétorio onde você abriu o vim.
	:saveas /file		salvar no dirétorio especificado por você.
	:q			sair
	:q!			forçar saída sem salvar.

	:bn			mudar para o proximo buffer.		|buffers
	:bp			mudar para o buffer anterior.		|veja legenda
	:bd			fechar o buffer.			|para mais
	:ls			listar todos os buffers abertos.	|detalhes.

	:split	/file		abrir outro arquivo para tela dividida na horizontal.
	:vsplit	/file		abrir outro arquivo para tela dividida na vertical.

	:colorschereme NOME	alterar o esquema de cores dos códigos no vim.

	:set number		ativar numeração de linhas.
	:set nonumber		desativar numeração de linhas.

	:set relativenumber	ativar numeração de linhas relativas ao cursor.
	:set norelativenumber	desativar numeração de linhas relativas ao cursor.

	:set autoindent		ativar autoidentação.
	:set noautoindent	desativar autoidentação.

	:registers		mostrar o conteúdo dos registradores.

	:set paste		ativar clipboard do sistema.
	:set nopaste		desativar clipboard do sistema.

	:set nowrap		desativar quebra de linha.
	:set wrap		ativar quebra de linha.

	:%s/argum/algum/g	substituir padrão por outro sem perguntar.
	:%s/consola/console/gc	substituir padrão por outro perguntando em cada ocorrência.
```
##Documentação Oficial Completa Em Inglês

[vimhelp.org](https://vimhelp.org/)

