# VIM

<figure>
	<img src="https://comparasoftware-192fc.kxcdn.com/wp-content/uploads/2018/08/logovim.png" alt="Imagem quebrada">
</figure>
<p>
	O editor de texto altamente configurável para programadores.
</p>

## Sobre

<p>
	pt-BR Um manual de consulta rápida e prática para iniciantes
	do editor de texto VIM ou NEOVIM. Matenha-o em uma janela para
	eventuais consultas. Obrigado por ler-lo, tenha um dia bom e muito produtivo.
</p>

## Autor

Escrito por: Luiz Paulo de Lima Araújo

## Legenda

```
	No modo normal e visual digitar um número antes da
	combinação de teclas modificará em número a ação.
	Exemplos:
		10gg vai para linha 10.
		gg vai para a primeira linha.
		5dd vai deletar 5 linha para baixo.
		8> vai colocar 8 tabulações na área selecionada no modo Visual.
		5>> vai indentar uma vez às cinco linhas abaixo.

	Registradores - armazenam informação textual.
		somente leitura
			: último comando.
			. último texto que você inseriu.
			% nome do arquivo corrente.
			# nome do arquivo editado anteriormente.
		 leitura e escrita
			" registrador padrão para onde vai deleção, cópia
			  implícita.
			0 auxiliar do registrador acima, atuando como
			  um secundário.
			1 até 9	fila de deleção, conteúdo mais recente
			  fica em 1 e mais antigo fica em 9.
			- auxiliar dos registradores numéricos, evitando
			  o enchimento rápido da fila. deleção vem para aqui.
			[a-z][A-Z] registradores de uso geral para você usar
			para armazenar texto.
			+ clipboard do sistema
			- registrador buraco negro, caiu aqui já era.
			/ registrador de última busca
	Use o commando :registers para visualizar os seus respectivos conteúdos.

	Buffers - Vários arquivos de textos abertos em simultâneo.
	Digamos que você abriu vários textos com o vim assim:
	$vim a.txt b.txt c.txt
	Verás apenas um buffer com apenas um texto na tela principal do editor.
	use os comandos :bn :bp para mover por entre esses buffers abertos.
	:bdelete ou :bd para deletar o buffer (não o arquivo).
	:split ou :vsplit para dividir a tela respecivamente na: horizontal ou vertical.
```

## Uso básico

### Modo Inserção i

```
	home		move o cursor para o início da linha.
	end		move o cursor para o fim da linha.
	insert		vai para o modo substituição.
	del		apaga letra sob o cursor.
	page_up		rolar o texto para cima.
	page_down	rolar o texto para baixo.

	ctrl shift v	colar texto do clipboard do sitema para o vim. Ou shift insert.

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

	ctrl n 		autocompletar com palavras pre-existentes.
	ctrl p 		autocompletar com palavras pre-existentes.
```

### Modo Visual v    OU    Modo Visual V (visual block)

```
	U		mudar área selecionada para maiúscula(caixa-alta).
	u		mudar área selecionada para minúscula(caixa-baixa).

	>		adicionar mais 1 ou N tabulações para área selecionada.
	<		adicionar menos 1 ou N tabulações para área selecionada.

	c		apaga área selecionada e vai para o modo INSERT (c change).
	d		apaga área selecionada e vai para o modo NORMAL (d delete).
	y		copia área selecionada e vai para o modo NORMAL (y yank).
```

### Modo Normal esc

```
	a		Modo insert no fim da linha.
	i		Modo insert.
	I		Modo insert no comesso da linha.
	v		Modo visual.
	V		Modo visual em bloco retangular.
	R		Modo replace.

	r		replace da letra em que o cursor esta em cima.

	"AB		gravar registrador de textos onde A é o nome do
			registrador e B é a operação a ser feita
			(p-paste y-yank d-delete c-change).

	o 		cria linha vazia abaixo, vai para ela, e entra em insert.
	O 		cria linha vazia acima , vai para ela, e entra em insert.

	ctrl r		refazer
	u		desfazer
	p		colar conteúdo previamente copiado ou cortado (p paste).

	yy		copiar linha inteira onde o cursor está (y yank).
	dd		deleta-copia a linha inteira onde o cursor está (d delete).

	dw		apagar palavra para frente (dw delete word).
	x		apagar letras a frente do cursor.

	d$		apagar do cursor até o fim da linha.
	d0		apagar do cursor até o comesso da linha.
	
	qq		comessar ou parar de gravar um MACRO.
	@q		colar MACRO gravada.

	/padrão		localizar um padrão de cima para baixo.
	?padrão		localizar um padrão de baixo para cima.
	n		mostrar o próximo padrão encontrado.

	g		ir para linha especificada por número. Apenas g vai para comesso do arquivo.
	G		ir para linha especificada por número. Apenas G vai para fim do arquivo.

	w		mover cursor para frente pelo comesso das palavras.
	e		mover cursor para frente pelo fim das palavras.
	b		mover cursor para traz pelo comesso das palavras.

	$		mover cursor para o fim da linha.
	0		mover cursor para o comesso da linha.

	}		mover cursor para o parágrafo abaixo.
	{		mover cursor para o parágrafo acima.

	(		mover cursor para o parágrafo acima com linha inicial.
	)		mover cursor para o parágrafo abaixo com linha inicial.

	j		mover cursor para baixo.
	k		mover cursor para cima.
	h		mover cursor para esquerda.
	l		mover cursor para direita.

	J		fundir a linha de baixo com a atual.

	mx		marcar atual posição do cursor.
	'x		saltar para última posição marcada.
	''		voltar para linha que o cursor estava antes do salto, vai e volta.
	'.		saltar para última linha que você modificou.

	ctrl y		rolar texto uma linha para cima.
	ctrl e		rolar texto uma linha para baixo.

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

```

### Linha De Comando :

```
	:help	COMANDO		obter ajuda acerca de um comando do vim.

	:e /file		abrir um arquivo do diretório especificado.
	:w			salvar no dirétorio onde você abriu o vim.
	:saveas /file		salvar no dirétorio especificado por você.
	:q			sair
	:q!			forçar saída sem salvar o arquivo ou os arquivos que você modificou.

	:bn			mudar para o proximo buffer.
	:bp			mudar para o buffer anterior.
	:bd			fechar/deletar o buffer corrente.
	:ls			listar todos os buffers abertos.

	:split	/file		abrir outro arquivo para tela dividida na horizontal.
	:vsplit	/file		abrir outro arquivo para tela dividida na vertical.

	:colorschereme NOME	alterar o esquema de cores da coloração de sintaxe do vim.
	:set background=	pode ser dark ou light.
	:set mouse=a		para que o mouse possa interagir com o vim.

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

## Replace R

```
	atalhos do modo insert funcionam aqui.
```


## Documentação Oficial Completa Em Inglês para o VIM

[vimhelp.org](https://vimhelp.org/)

## Para o NEOVIM

[neovim.io/doc](https://neovim.io/doc/)

