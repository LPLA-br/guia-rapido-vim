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
			_ registrador buraco negro, caiu aqui já era.
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

## Uso Básico

### Modo Inserção i

```
    esc         sair do modo insert.
    home	    move o cursor para o início da linha.
	end		    move o cursor para o fim da linha.
	insert		vai para o modo substituição.
	del		    apaga letra sob o cursor.
	page_up		rolar o texto para cima.
	page_down	rolar o texto para baixo.

	ctrl shift v	colar texto do clipboard do sistema para o vim.
    shift insert.   colar texto do clipboard do sistema.

	ctrl t		insere tabulação no início da linha.
	ctrl d		apaga tabulação no início da linha.
    0 ctrl d	apaga todas as tabulações da linha.

	ctrl e		recria o caractere abaixo do cursor para a linha atual.
	ctrl y		recria o caractere acima  do cursor para a linha atual.

	ctrl c		voltar para o modo normal.
	ctrl a		iserir trecho previamente salvo.

	ctrl r R	colar conteúdo do registrador, onde R é o nome do registrador.

	ctrl u 		deletar todo o conteúdo de onde o cursor está até o início da linha.
	ctrl w		deletar palavra antes do cursor.

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

    {NOTAS}
    O poder do visual block
    Modo visual bloco isola uma área
    onde comandos atuam somente nesta.
    copias,colas,deleções,substituições
    com regex, indentações, armazenamento
    em registadores e etcetera.

```

### Modo Normal esc

```
    {MODOS DE EDIÇÃO}
	a		Modo insert no fim da linha.
	i		Modo insert.
	I		Modo insert no comesso da linha.
	R		Modo replace.
	v		Modo visual.
	V		Modo visual para a linha inteira.
	ctrl+v	Modo visual em bloco quadrado (extremamente útil).


    
    {REMOÇÃO DE CONTEÚDO ENTRE FECHANTES}
    diX     remover conteúdo entre {} () "" '' `` ´´
            X=caractere que fecha outro.



    {REFAZER E DESFAZER}
	ctrl r	refazer
	u		desfazer

    {MOVIMENTAÇÃO BÁSICA}
	j		mover cursor para baixo.
	k		mover cursor para cima.         kima
	h		mover cursor para esquerda.     jaixo
	l		mover cursor para direita.

	g		ir para linha especificada por número. Apenas g vai para comesso do arquivo.
	G		ir para linha especificada por número. Apenas G vai para fim do arquivo.

	w		mover cursor para frente pelo comesso das palavras.
	e		mover cursor para frente pelo fim das palavras.
	b		mover cursor para traz pelo comesso das palavras.

	$		mover cursor para o fim da linha.
	0		mover cursor para o comesso da linha.
    ^       mover cursor para o comesso da linha.

	}		mover cursor para o parágrafo abaixo.
	{		mover cursor para o parágrafo acima.

	(		mover cursor para o parágrafo acima com linha inicial.
	)		mover cursor para o parágrafo abaixo com linha inicial.



	ctrl y		rolar texto uma linha para cima.
	ctrl e		rolar texto uma linha para baixo.

	H		mover cursor para o topo da tela.
	M		mover cursor para o meio da tela.
	L		mover cursor para o fim da tela.



    {REGISTRADORES}
	"AB		gravar registrador de textos onde A é o nome do
			registrador e B é a operação a ser feita
			(p-paste y-yank d-delete c-change).
            Pode ser registrador: [a-z][A-Z][1-9]



    {MACROS}
	qA		gravar macro. A= registrador [a-z][A-Z][1-9]
	@A		executar MACRO gravada. A= registrador [a-z][A-Z][1-9]
    @@      repetir



    {POSIÇÕES DO CURSOR}
	mX		marcar atual posição do cursor, onde X é um registrador de posição [a-z][A-Z][1-9].
	'X		saltar para última posição marcada, onde X é o registrador que contém a posição.
	''		voltar para linha que o cursor estava antes do salto, vai e volta.
	'.		saltar para última linha que você modificou.



    {DOBRAS}
    zfND    dobrar (fold). N corresponde a número de linhas para; D corresponde a: j=cima k=baixo.
            dobra N linhas de modo a ocuta-lhas.
    zo      abre (open) linha dobrada.
    zc      fecha (close) linha com dobra.



    {COPIAR, COLAR E DELETAR}
	yy		copiar linha inteira onde o cursor está (y yank).
    Y       faz a mesma coisa que o acima.
    yw      copiar palavra da posição do cursor até o fim dela.
	p		colar conteúdo previamente copiado ou cortado (p paste).
	dd		deletar a linha inteira onde o cursor está (d delete).
    dw      deletar a palavra da posição do cursor até o fim dela (delete word).
    D       deletar do cursor até fim da linha (faz o mesmo que d$).
	x		deletar letra por letra a frente do cursor.
	d$		deletar do cursor até o fim da linha.
	d0		deletar do cursor até o comesso da linha.
	


    {BUSCA POR PADRÕES NO TEXTO}
    /padrão		localizar um padrão de cima para baixo.
	?padrão		localizar um padrão de baixo para cima.
	n		mostrar o próximo padrão encontrado.



    {JANELAS}
	ctrl ww		mudar foco da tela dividida.
	ctrl wv		divide o texto atual em duas janelas verticais.
	ctrl ws		dividir texto atual em duas janelas horizontais.
	ctrl w+		aumentar altura da janela onde se encontra o cursor.
	ctrl w-		diminuir altura da janela onde se encontra o cursor.
	ctrl w<		diminuir largura da janela onde se encontra o cursor.
	ctrl w>		aumentar largura da janela onde se encontra o cursor.
	ctrl w=		fazer todas as janelas terem a mesma largura e altura.
	ctrl wr		rotacionar janelas.
	ctrl wq		fechar janela em que o cursor se encontra.


    {OUTROS}
	o 		cria linha vazia abaixo, vai para ela, e entra em insert.
	O 		cria linha vazia acima , vai para ela, e entra em insert.

	r		replace. Troca letra em que o cursor está em cima.

	J		fundir a linha de baixo no fim da linha atual(interessante).
    K       abre manual man para a palavra abaixo do cursor.

```

### Linha De Comando :

```
	:help	COMANDO		obter ajuda acerca de um comando do vim.

    {ARQUIVO}
	:e /file		    abrir um arquivo do caminho especificado.
	:w			        salvar (recebe argumento de nome se o arquivo novo não tem nome).
	:saveas /file		salvar no dirétorio especificado por você.
	:q                  sair (não sai se as modificações do arquivo não foram salvas).
	:q!                 forçar saída sem salvar o arquivo ou os arquivos que você modificou.

    {BUFFERS}
	:bn                 mudar para o proximo buffer.
	:bp                 mudar para o buffer anterior.
	:bd                 fechar/deletar o buffer corrente.
	:ls                 listar todos os buffers abertos.

    {TEXTOS EM TELA DIVIDIDA}
	:split	/file		abrir outro arquivo para tela dividida na horizontal.
	:vsplit	/file		abrir outro arquivo para tela dividida na vertical.

    {BUSCA E SUBSTITUIÇÃO}
    Linha em que o cursor se econtra.
	 :s/argum/algum/g	    substituir padrão por outro sem perguntar.
	 :s/consola/console/gc	substituir padrão por outro perguntando em cada ocorrência.
    Todas linhas:
	 :%s/argum/algum/g	    substituir padrão por outro sem perguntar.
	 :%s/consola/console/gc	substituir padrão por outro perguntando em cada ocorrência.
    De uma linha até outra
     :3,10s/a/b/g           substituir sem perguntar da linha 3 até a 10
     :3,10s/a/b/gc          substituir perguntando da linha 3 até a 10


    {OUTROS}
	:colorschereme NOME	    alterar o esquema de cores do colorimento de sintaxe do vim.
	:set background=	    pode ser dark ou light.
	:set mouse=a		    para que o mouse possa interagir com o vim.

    :set number             ativar numeração de linhas.
	:set nonumber		    desativar numeração de linhas.

	:set relativenumber     ativar numeração de linhas relativas ao cursor.
	:set norelativenumber	desativar numeração de linhas relativas ao cursor.

	:set autoindent		    ativar autoidentação.
	:set noautoindent	    desativar autoidentação.

	:registers		        mostrar o conteúdo dos registradores.

	:set paste		    ativar clipboard do sistema.
	:set nopaste		desativar clipboard do sistema.

	:set nowrap		    desativar quebra de linha.
	:set wrap		    ativar quebra de linha.

```

## Replace R

```
	atalhos do modo insert funcionam aqui.
```

## Plugins com gerenciador de Plugins VimPlug

[vimplug](https://github.com/junegunn/vim-plug)

## Documentação Oficial Completa Em Inglês para o VIM padrão.

[vimhelp.org](https://vimhelp.org/)

## Para o NEOVIM, o vim melhorado.

[neovim.io/doc](https://neovim.io/doc/)

