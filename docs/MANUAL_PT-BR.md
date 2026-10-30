# BeautyShot 82 — Manual do usuário

## 1 · Comece aqui

BeautyShot é um aplicativo Windows para apresentação de assets 3D: materiais, iluminação, câmeras, animação e saída em imagem ou vídeo. Este manual descreve a interface da Beta 82. Os controles dependem do objeto, da família do material e do renderizador selecionados; opções que não se aplicam podem ficar ocultas.

### Instalar e abrir
Extraia todo o download para uma pasta com permissão de escrita. Mantenha as pastas Engine e SculptStudio junto do executável de entrada; copiar apenas o executável não instala o aplicativo. Abra o BeautyShot pela pasta extraída, nunca de dentro do ZIP. Guarde projetos e renders em outra pasta para que a atualização do aplicativo não substitua seu trabalho.

A build distribuída destina-se a Windows de 64 bits e DirectX 12. Path tracing progressivo e offline exigem GPU e driver compatíveis com ray tracing por hardware. As opções DLSS exigem hardware NVIDIA compatível. Um recurso funcionar em um renderizador não comprova suporte em outro. A máquina de referência desta versão tem RTX 4060 de 8 GB e 32 GB de RAM; é uma configuração testada, não um requisito mínimo universal nem garantia de desempenho.

### Sua primeira imagem
1. Escolha Arquivo > Importar malha. Aguarde a conclusão da geometria e das texturas.
2. Selecione uma peça em Cena e seu slot de material. Atribua base color, normal e roughness em Materiais.
3. Em Ambiente, escolha um HDRI ou céu procedural. Ajuste as luzes em Lighting.
4. Navegue até um enquadramento útil. Enquadre tudo ou a seleção se o modelo estiver fora da vista.
5. Crie uma câmera a partir da vista, defina a resolução e trave-a depois de compor a imagem.
6. Salve o projeto. Em Render, escolha tarefa de imagem, câmera, formato e destino. Use PNG para uma imagem pronta para exibição; EXR para composição linear.

Para texturas que já contêm iluminação pintada, use Qualidade da viewport > NPR > Unlit / Hand-painted. Comece com a cor do material branca e vertex color desligado. O procedimento específico está no capítulo NPR.

## 2 · Área de trabalho e navegação

A barra de menus fica no topo. Cena e o inspetor contextual Objeto ficam à esquerda; Materiais fica à direita. A viewport ocupa o centro, com seletor de câmera, ferramentas de transformação e cubo de navegação. A barra inferior informa importação, carregamento de texturas e contagem de triângulos. A Timeline abre abaixo da viewport.

Clique em um objeto para selecioná-lo. Use o Outliner quando superfícies sobrepostas dificultarem a seleção. Enquadre a seleção antes de orbitar um detalhe pequeno. A barra de ferramentas alterna mover, girar e escalar, espaço de coordenadas, encaixe e seleção de peças. Alterar o espaço de transformação muda os eixos do gizmo; isso não gira o objeto por conta própria.

A navegação é configurável. Em Preferências > Navegação, escolha perfil, centro de órbita e comportamento do foco. O rodapé mostra dicas do perfil ativo. O centro de órbita pode usar pivô da vista, seleção ou ponto sob o cursor. O foco pode enquadrar a seleção ou manter a posição da câmera. Eixo e direção do arrasto de dolly são ajustáveis. Copie vínculos ou parta de um preset antes de personalizar.

Shift + arrasto com botão direito gira o HDRI. Ctrl + Shift + arrasto com botão direito gira o rig de luzes; o primeiro movimento trava o eixo até soltar. O cubo de navegação escolhe vistas padronizadas e Home retorna à vista inicial. Oculte-o pelo menu ou ajuste seu tamanho em Preferências.

Arraste divisórias para redimensionar os painéis. Janela permite destacar Cena/propriedades ou Materiais, mover o aplicativo ao próximo monitor e restaurar o layout. Layouts nomeados guardam arranjos úteis. Restaurar layout altera a interface, não as transformações dos objetos.

Controles numéricos aceitam valores digitados; Shift torna o arrasto mais preciso. O indicador de valor modificado permite voltar ao padrão. Clique com o botão direito em rótulos compatíveis para adicionar ou remover Favoritos. O conta-gotas do seletor de cor captura uma cor visível; Esc cancela.

## 3 · Referência dos menus

### Arquivo
Novo inicia um projeto. Abrir carrega um projeto salvo. Importar malha adiciona geometria à cena atual. Salvar atualiza o projeto; Salvar como cria outro arquivo. Empacotar projeto reúne recursos externos compatíveis para transferência. Recuperar autosave abre uma cópia de recuperação: confira-a e salve com outro nome antes de substituir o projeto principal.

### Editar
Desfazer e Refazer percorrem o histórico de edições. Duplicar cria cópias dos itens selecionados. Agrupar reúne peças; Desagrupar desfaz o agrupamento sem excluir seus membros. Excluir remove o item selecionado; excluir um grupo também remove os objetos contidos nele. Isolar e Restaurar permitem trabalhar temporariamente só com a seleção. Ocultar, Mostrar tudo, Travar e Destravar tudo controlam visibilidade e edição. O histórico da câmera é separado do histórico geral.

### Adicionar
Primitivas incluem esfera, plano, cubo e cilindro. Luzes incluem retangular, pontual, spot e sol. Câmera cria uma câmera a partir da vista; alvo de foco fornece um ponto móvel para a profundidade de campo. Submenus de efeitos são preenchidos pela biblioteca instalada: atmosfera/fog local, partículas, god rays e Draw FX. O fog volumétrico global fica em Ambiente. Draw FX inicia o desenho; Parar desenho ou Esc encerra. Fire scatter usa a superfície selecionada quando disponível.

### Janela
Histórico abre ferramentas de histórico/câmera. Câmera, Timeline, Ambiente, Render e Preferências abrem seus painéis. Mover para o próximo monitor troca a tela da janela principal. Escala oferece 100%, 125% e 150%. Destacar/reencaixar Cena e propriedades e Destacar/reencaixar Materiais alternam painéis flutuantes e encaixados. Mostrar/ocultar Cena e Materiais controlam sua visibilidade. Layouts de painéis gerencia arranjos salvos. Restaurar layout volta ao encaixe padrão.

### View
Perspectiva retorna à projeção em perspectiva. Vistas ortográficas oferece Frente, Trás, Esquerda, Direita, Topo e Base. Mostrar grid ortográfico alterna a grade. Enquadrar tudo ajusta a vista à cena visível. Passes abre canais de diagnóstico. Qualidade da viewport abre os controles de renderizador e desempenho.

### Menu de câmera da viewport
Ver através de escolhe Vista livre, uma câmera da cena ou Nova câmera a partir da vista. Renderizador da viewport escolhe Realtime, Progressive path tracing, Hybrid ou NPR. Layout escolhe Vista única, Prévia de câmera, Duas vistas ou Quatro vistas. Opções das vistas abre tamanho, frequência de atualização e iluminação das prévias. O pequeno cadeado ao lado trava ou destrava a câmera de render ativa.

### Botões do cabeçalho
Desfazer, Refazer, Mostrar/ocultar painéis, Preferências e Render dão acesso direto. Render executa a tarefa configurada, que pode não ser uma imagem estática. O ícone da timeline alterna sua exibição. Minimizar, maximizar e fechar podem estar na barra de título do Windows, conforme o modo de janela.

## 4 · Projetos, importação e portabilidade

Salve cedo, principalmente antes de importar um asset pesado. O projeto registra composição, atribuições e ajustes; ele não substitui as malhas e texturas de origem. Mantenha esses recursos em uma pasta estável. Use Empacotar projeto para transferir o trabalho e abra a cópia empacotada para conferir os caminhos.

Importe por Arquivo > Importar malha ou pelo arrasto compatível. O filtro do diálogo de arquivos indica os formatos aceitos nesta build. Importar malha e importar groom Alembic são operações distintas; dados de animação ou cabelo não são equivalentes a uma malha estática. Preferências de importação controlam a separação por peças/IDs de material. Assim, um personagem pode aparecer como grupo com peças e slots editáveis separadamente.

O holograma é uma prévia de carregamento. A geometria aparecer não significa que todas as texturas estejam prontas. Confira a barra inferior e aguarde antes de avaliar o material ou iniciar um render final. Fontes muito grandes podem exigir bastante RAM, VRAM e tempo, mesmo que o asset visível pareça simples.

Reimportar selecionado atualiza um objeto pela origem preservando posicionamento e materiais atribuídos. Reimportar somente esta peça atualiza uma parte de uma origem com múltiplas peças. O seletor de peça e o mapeamento de materiais definem o que será substituído. Confira essas escolhas após renomear partes no programa de modelagem.

Se faltar um arquivo, restaure-o no caminho salvo ou aponte o canal/origem para a localização nova. Salve uma cópia corrigida e empacote novamente. Autosave auxilia a recuperação, mas não substitui controle de versões. Faça backups datados antes de mudanças destrutivas e de abrir trabalhos antigos em uma beta nova.

## 5 · Cena, grupos e transformações

O Outliner de Cena reúne ambiente, iluminação, pós-processamento, render, qualidade da viewport, câmeras, grupos e peças. A busca filtra a lista exibida. Filtros por tipo não alteram a visibilidade da cena. Expanda grupos e objetos para acessar peças e slots de material.

Clique no olho para mostrar ou ocultar. Arraste sobre vários olhos para alterar itens em um gesto; um Desfazer restaura esse gesto. A trava impede a edição do item correspondente. O pequeno cadeado de câmera controla sua transformação. Selecione o slot de material para editar a atribuição correta, especialmente em superfícies sobrepostas.

Agrupe peças que precisam mover ou animar juntas. Selecione o próprio grupo para animar a transformação do personagem inteiro. Excluir um grupo exclui os objetos contidos nele; use Desagrupar para mantê-los. Isole a seleção em cenas densas e restaure a visibilidade antes da saída final.

O inspetor Objeto apresenta posição, rotação e escala. Gizmos de mover/girar/escalar usam o espaço de coordenadas escolhido. Snapping facilita deslocamentos regulares. Escalas negativas ou muito desiguais podem afetar normais, espessura e padrões procedurais; confira os materiais depois. Vista explodida separa peças para apresentação sem exigir posicionar cada parte manualmente.

Editar pivô altera o centro das transformações. Escolha uma das 27 posições da caixa envolvente, digite coordenadas, copie um pivô, procure o vértice mais próximo ou escolha um vértice na viewport. Saia da edição do pivô antes de mover o objeto. Aplicar pivô/definir origem torna esse ponto a origem mantendo a malha no lugar. Confira o pivô antes do turntable: um pivô deslocado faz o personagem orbitar em vez de girar sobre si.

Mesh / Subdivision reúne controles disponíveis de refinamento da geometria. Mais geometria nem sempre ajuda: avalie silhueta e sombreamento, preservando a origem para reimportação. Visibilidade no render e seleção no editor são coisas diferentes; confirme os objetos que aparecerão na saída.

## 6 · Biblioteca de materiais e presets

A biblioteca reúne materiais da cena e categorias de presets. Busca, categorias e Favoritos facilitam encontrar um preset. Ajuste o tamanho das miniaturas. A miniatura ilustra o material nas condições de sua prévia; a aparência muda em outro modelo, iluminação ou renderizador.

Arraste um preset para uma superfície ou slot no Outliner. Alt + arrasto abre opções de abrangência. Duplo clique adiciona um material editável à biblioteca da cena. Confirme o slot antes de editar: vários objetos podem compartilhar o mesmo material, e a alteração afetará todos eles. Duplique o material quando uma peça precisar de ajustes independentes.

Use categorias e Mover para para organizar entradas selecionadas. Favorito marca materiais frequentes. Salve/exporte um preset para reutilizar o look e importe presets compatíveis à biblioteca local. Mantenha as texturas dependentes junto dele ao compartilhar. Um preset de material não contém toda a iluminação e composição da câmera.

Abrir Material Graph ou Open construction apresenta a construção editável. Controles de artista oferecem ajustes comuns; Avançado lista parâmetros reais do material pai preparado. Essas vistas editam dados relacionados, não cópias independentes. Alguns presets usam texturas especiais ou switches compilados que exigem uma variante preparada, em vez de simples substituição de arquivo.

Prismatic Crystal é um material para superfícies escolhidas, não um estilo NPR global. Aplique-o somente onde quiser aparência de cristal; use o seletor NPR para o estilo artístico da viewport.

## 7 · Canais de textura e interpretação de cor

Selecione o material e coloque cada mapa no canal correspondente. Base color descreve a cor; normal descreve detalhes de direção; roughness controla a abertura do brilho; metallic identifica metal; AO controla oclusão ambiente; emissive adiciona cor emitida. Mapas empacotados exigem escolher o canal de origem correto em cada destino. Nem toda textura em tons de cinza é opacidade.

Cada mapa pode ser ligado/desligado sem perder arquivo, tiles ou ajustes. Abrir pasta da origem localiza o arquivo. Restaurar mapa retorna ao padrão/herdado quando disponível. Texturas de presets podem ser herdadas até serem substituídas. Canais de origem escolhem R, G, B ou A. Alterações de espaço de cor geram uma textura convertida compatível, em vez de forçar um sampler incompatível.

Base color costuma conter dados de cor; roughness, metallic, AO e normal são dados lineares. Siga a convenção do programa de origem, em vez de compensar uma interpretação errada com exposição. Normais podem ser DirectX ou OpenGL; use o controle de interpretação quando relevos parecerem invertidos. Intensidade regula a força do detalhe.

Roughness ou Glossiness define a interpretação. Glossiness é invertido para roughness em dados lineares. Níveis/gamma e inversão são ajustes do canal, independentes da exposição da cena. O threshold de metallic pode separar metal/dielétrico de forma binária; deixe-o desligado para valores contínuos intencionais. AO tem seus próprios níveis. A prévia de canal isola dados para diagnóstico.

Escala UV, repetição de detalhe, detail normal, height/parallax e sharpen modificam amostragem ou relevo aparente. A amostragem UV/UDIM da cor deve acompanhar a origem. Antes de atribuir uma costura ao shader, confira padding, convenção de normal, canal e textura original. Pintura de superfície e vertex color podem multiplicar a cor; desligue Use vertex color ao comparar só a textura. O fluxo de carregar base map privilegia a textura, mas confira ajustes já salvos no projeto/preset.

Tint e níveis de base color são alterações artísticas intencionais. Para comparar com a origem, comece com tint branco, níveis neutros, espaço de cor correto e sem modulação de vértices. Transformação de exibição e pós-processamento ainda podem mudar a imagem da tela.

## 8 · Opacidade, pixels pretos e vidro

Cor preta e transparência são independentes. Um pixel preto opaco deve continuar sendo uma superfície preta visível. A máscara de cobertura define se a superfície existe. O alpha do base color pode fornecer cobertura quando configurado; a luminosidade RGB não substitui esse alpha.

### Escolher o modo de cobertura
Opaque mantém a superfície sólida. Mapas de opacidade guardados são ignorados por materiais opacos, inclusive no NPR. Cutout / Masked remove pixels conforme a cobertura e serve para folhas, renda ou recortes de hair cards. Translucent permite cobertura parcial, com comportamento de ordenação e render distinto. Para vidro ou plástico transparente, escolha Glass em vez de apenas reduzir a opacidade de uma superfície com espalhamento.

### Diagnosticar regiões pretas desaparecendo
1. Selecione o slot afetado e confira Opacity mode.
2. Para objeto sólido, escolha Opaque. Confira o canal Opacity e o indicador de alpha do Base color.
3. Veja o alpha da textura separado do RGB. Um PNG pode ter alpha zero indesejado mesmo que a imagem RGB pareça correta.
4. Para recortes intencionais, mantenha Masked e forneça a máscara correta. Não elimine alpha legítimo para esconder outro problema.
5. Exporte um PNG RGBA pequeno e veja sobre um xadrez. Fundo preto do visualizador pode esconder a diferença entre preto e transparência.

Subsurface e thickness não são cobertura. Branco na máscara SSS habilita espalhamento; preto o reduz. Thickness muda a distância percorrida pela luz. Para uma garrafa, comece com cobertura 1 e ajuste distância de absorção, cor de transmissão, IOR e roughness. Vidro precisa de geometria, espessura e ambiente adequados para refletir. Realtime e path tracing podem diferir; um plano fino não é um volume fechado físico.

Para saída transparente, escolha formato com alpha e habilite a opção de alpha da saída. JPEG e MP4 comum não preservam fundo transparente. Cobertura do material e alpha do fundo da imagem são configurações separadas.

## 9 · Famílias de materiais e controles avançados

Escolha uma família adequada: PBR geral, pele/subsurface, metal, clear coat, tecido/fuzz, vidro, hair cards ou olhos. Os parâmetros variam por família. Comece pelos controles básicos; Artista e Avançado expõem outras capacidades do material pai preparado. Pesquise parâmetros e confira o tipo antes de alterar.

Perfis de pele, força de transmissão, espessura e cor de espalhamento regulam subsurface. Clear coat adiciona uma camada refletiva com roughness próprio. Tecido/fuzz controla resposta de fibras. A opacidade de hair cards recorta cartões; não cria fios de groom. Olhos incluem máscara e profundidade da íris. Receitas de vidro são pontos de partida, não substitutos da geometria correta.

Grupos de iluminação separam luz direta e resposta especular. Superfície de um/dois lados muda a resposta de faces traseiras. Cor, mapa e intensidade emissivos controlam emissão. Para brilho só em materiais escolhidos, marque Bloom seletivo neles e ajuste raio/intensidade em Pós-processamento. Pode ser combinado com bloom da cena; material emissivo brilhante não equivale automaticamente a uma luz de área em todo renderizador.

Materiais procedurais/argila podem oferecer escala automática, repetição e relevo. A escala automática ajusta o detalhe ao modelo; revise-a quando as unidades da origem produzirem detalhes inadequados. Entradas escalares, vetores, cores e texturas em Avançado editam parâmetros reais preparados. Switches marcados como compilados não geram variantes ausentes da build. Texturas cube, volume e virtual podem exigir variante preparada.

O inspetor de capacidades descreve a família real de render. Ele não promete compilar qualquer grafo Unreal dentro do aplicativo distribuído. Duplique o material antes de mudar sua família e compare os canais depois.

## 10 · Grafo de materiais e pintura de superfície

Abra Material Graph pela biblioteca para inspecionar a construção. Selecione nodes, edite entradas e conecte saídas compatíveis. Mantenha a saída final conectada. Controles publicados de artista usam os mesmos valores dos nodes no grafo e, quando animáveis, da timeline.

Agrupar seleção (Ctrl+G) organiza nodes; Desagrupar (Ctrl+Shift+G) expande-os. Salvar seleção como preset guarda uma construção reutilizável. Inserir material Blend oferece o fluxo de mistura em camadas compatível. Um grafo baseado em família preparada precisa respeitar suas capacidades em runtime; não é um compilador geral de shaders Unreal.

Para animar um material, adicione/use um node Float animável, exponha o controle escalar/cor e crie a faixa do material. Nomes inválidos de parâmetros nativos são rejeitados. Percorra a timeline para conferir o mesmo valor publicado e salve o projeto para preservar construção e animação. Switch estático não pode ser animado como valor escalar.

Pintura de superfície oferece pincel e seleção de faces. Configure raio, força, falloff, cor, operação e canal. No modo Brush, o botão esquerdo pinta; em Faces, clique ou selecione por caixa, Ctrl adiciona e Shift remove. A navegação mantém seus atalhos. Preencher objeto/faces selecionadas aplica a operação ao escopo escolhido. Slot-only limita ao slot selecionado quando ativado.

Escolha um material de pintura ou adicione camada pintada para misturar materiais. A prévia ajuda a conferir o canal. Pintura de vértices depende de vértices suficientes para representar detalhes; ela não cria uma textura UV com resolução arbitrária. Restaure a exibição normal após examinar máscaras e preserve a origem para decidir sobre reimportação.

## 11 · Groom e importação de curvas

A importação de groom Alembic cria geometria de fios a partir de curvas compatíveis. Defina unidades e eixo vertical em Preferências quando souber a convenção da origem. Unidades automáticas são um ponto de partida; confira a escala em relação ao personagem. Z-up e Y-up representam sistemas diferentes.

Selecione o groom e abra Geometria do Groom. Densidade interpola fios adicionais entre curvas próximas compatíveis; não recupera um penteado ausente da origem. Amostragem adaptativa usa mais pontos onde a curvatura exige: ângulo menor preserva cachos, enquanto trechos retos precisam de menos pontos.

O multiplicador de largura escala as larguras originais dos vértices, preservando o afunilamento de fontes compatíveis, como XGen. Confira raízes e pontas, além da silhueta. Largura e densidade excessivas podem deixar o cabelo sólido e aumentar o uso de memória.

Reconstruir relê a origem com os ajustes atuais. Restaurar original relê com densidade 1× e amostragem original. Mantenha o Alembic acessível; reconstrução depende desse arquivo. Teste um recorte pequeno antes de elevar a densidade do groom inteiro.

## 12 · Luzes e rigs de iluminação

Adicione luz retangular, pontual, spot ou sol pelo menu Adicionar ou controle de luz no Outliner. Retangulares criam reflexos de área; pontuais irradiam de uma posição; spots têm cone; sol fornece direção. Selecione a luz para editar transformação, potência e cor. Presets de temperatura são pontos de partida; tint continua sendo uma escolha artística.

Tamanho da fonte e suavidade moldam brilhos e sombras quando disponíveis. Perfis IES definem distribuição fotométrica; Gel/Gobo molda ou colore a projeção. Carregue recursos compatíveis e mantenha-os no pacote do projeto. Gobo não equivale a trocar a imagem de fundo do ambiente.

Light Controller e controles do rig movem um conjunto de luzes de forma coerente. É possível restaurar rotação e enquadrar o rig. Potência em EV muda a intensidade do conjunto. Seguir objeto mantém a relação configurada com o alvo. Confira alvo e centro antes de girar um rig ao redor de uma cena grande ou deslocada.

Controles especulares podem ocultar o brilho direto de uma luz preservando sua iluminação. Para pontual, spot e retangular, controles exclusivos do piso reduzem reflexos indesejados no chão sem retirar os brilhos do objeto. Grupos de iluminação nos materiais separam ainda mais luz direta e resposta especular.

Espalhamento volumétrico e sombras volumétricas regulam a participação no fog. Só são úteis com um meio volumétrico adequado. Shadow maps, virtual shadow maps e sombras ray traced são opções de qualidade da viewport, não tipos artísticos de luz. Compare um render pequeno no backend final depois de mudar iluminação ou sombras.

## 13 · Ambiente, piso e efeitos

Ambiente controla HDRI, céu, chão e fundo. A rotação do HDRI muda a direção da iluminação ambiental. Intensidade altera iluminação; visibilidade do fundo define se o ambiente aparece atrás do modelo. Ocultar o fundo não necessariamente desliga sua luz. Sky Light ativa a contribuição ambiente da fonte escolhida.

Céu procedural oferece outra fonte de céu. Ground controla presença e aparência do piso. Ajuste material/reflexo do chão em vez de escurecer a imagem inteira para reduzir seu brilho. Oclusão ambiente da cena adiciona contato na luz indireta e é independente dos mapas AO dos materiais.

O fundo da câmera pode ser cor sólida ou imagem. Preencher/Cover ocupa o recorte e pode cortar bordas; Conter/Contain mostra a imagem inteira e pode deixar margens; Esticar/Stretch preenche alterando proporção. Ajustar recorte à imagem muda a proporção de saída. Fundo chapado e fundo com profundidade respondem de formas diferentes ao movimento e posicionamento.

Fog volumétrico global é ativado em Ambiente. Efeitos locais de atmosfera são objetos separados com controles próprios. Use escala uniforme quando solicitado. Raio controla o volume esférico; densidades zero removem o fog. Avançado apresenta parâmetros do efeito preparado, que variam conforme o asset.

Draw FX cria um efeito por traço, depois editável por transformação. Escolha outro traço em Adicionar > Particle Effects > Draw FX; Esc encerra o desenho. Chama natural/estilizada, cor, direção, velocidade, gravidade, luz vinculada, malha e material personalizados só aparecem em efeitos compatíveis. Material padrão remove o override. Partículas e efeitos animados precisam de warmup para renderizar um estado estabilizado.

## 14 · Câmeras, lentes e múltiplas vistas

Vista livre é a câmera de navegação, não uma câmera de render salva. Crie uma câmera da vista para guardar a composição. Ver através da câmera a ativa. Uma moldura identifica o recorte; a indicação muda quando a câmera está travada. Destrave antes de alterar sua transformação e trave novamente para evitar movimentos acidentais.

Controles incluem órbita/yaw, inclinação, distância, transformação precisa e apontar para o centro. Perspectiva usa lente/FOV; projeção ortográfica elimina a mudança de tamanho com a profundidade. Escolha uma direção ortográfica pelo menu View ou cubo. Largura ortográfica controla enquadramento, não distância focal.

Saída/recorte define largura, altura e presets. Prévia do recorte mostra os limites da imagem. Margem, cor/opacidade das guias e sombreamento externo auxiliam composição sem mudar pixels finais. Duplicar câmera pode duplicar seus keyframes; excluir remove a vista. Histórico da câmera oferece recuperação separada de navegação/composição.

Profundidade de campo depende de distância de foco, abertura e lente/projeção. Use autofocus ou alvo de foco para assunto em movimento. Bokeh/forma da lente controla brilhos desfocados. Confira foco na resolução final: uma prévia pequena pode esconder um plano de foco errado. O alvo precisa continuar corretamente atribuído e animado quando o assunto se desloca.

Vista única, prévia de câmera, duas vistas e quatro vistas são layouts de trabalho. Tamanho e atualizações por segundo equilibram fidelidade e fluidez; iluminação completa pode custar mais. Cada vista tem seu contexto de interação. Ative a vista pretendida antes de manipular objetos ou luzes. Ter várias prévias não cria automaticamente uma fila de render de câmeras.

Look da câmera/override local permite pós-processamento próprio. Entre na câmera antes de editar seu look. O pós da cena continua sendo o padrão para câmeras sem override. A câmera escolhida em Render define a composição exportada.

## 15 · Pós-processamento e gerenciamento de cor

Escolha Pós-processamento da cena para um look comum ou Look da câmera/override local para uma câmera específica. Confira o destino antes de alterar exposição ou cor. Restaurar todos os efeitos atua no escopo selecionado; salve um preset de look se quiser reutilizá-lo.

Exposição/EV controla brilho. Temperatura e tint corrigem ou estilizam a cor. Saturação, contraste, gamma, ganho e offset mudam a resposta tonal. Curvas de imagem ajustam canais/tons; curvas neutras são uma boa base de comparação. Desative color grading para diagnosticar se uma mudança vem da correção de cor ou do material.

Bloom cria halo em valores brilhantes. Bloom seletivo restringe um brilho adicional aos materiais emissivos marcados; escolha se deseja combinar com bloom da cena. Vinheta escurece o perímetro. Sharpen, clareza e raio da clareza alteram contraste de detalhes. Aberração cromática/scene fringe separa cores nas bordas. Tamanho e intensidade do grão controlam textura de filme.

Efeitos de filme incluem grão adicional, croma e animação do grão quando disponíveis. Intensidade zero desliga o efeito. Grão animado é estável por quadro de saída; não é o mesmo que ruído de amostragem do path tracing. Limpar efeitos extras antigos remove efeitos guardados por cenas antigas para que os controles visíveis correspondam ao look.

Color lookup carrega LUT .cube com intensidade ajustável. A transformação de exibição, incluindo opções OCIO/tone mapping disponíveis, afeta viewport e imagens de exibição. Beauty linear EXR e passes de dados destinam-se a composição com gerenciamento de cor, não comparação direta em visualizador sem transform. Aplique a transformação de exibição adequada ao visualizá-los.

CMAA2 pode funcionar sozinho ou depois do AA da GPU; combinado preserva esse AA. Ele trata bordas espaciais, não ruído de iluminação. Ferramentas de calibração/ROI ajudam a comparar resposta de luz e textura. O processamento interno NPR é separado do pós da cena/câmera; trocar estilo não exige substituir o grading da cena.

## 16 · Renderizadores da viewport e desempenho

Realtime usa o caminho de iluminação interativo e ajuda na montagem. Progressive path tracing mantém a prévia por raios durante a navegação e refina ao parar. Hybrid navega em realtime e apresenta o resultado path traced após uma pausa. NPR aplica superfícies estilizadas e/ou pós interno do estilo. Escolha em Qualidade da viewport ou no menu de câmera da viewport.

Progressive e Hybrid dependem de ray tracing por hardware e shaders incluídos. Se indisponíveis, confira GPU/driver e uma cena pequena primeiro. Uma cena renderizar offline não significa que caiba nos limites de memória/inicialização interativos. Malhas densas, texturas grandes e múltiplas prévias contribuem para o consumo.

A reconstrução progressiva oferece Auto/prévia neural ou resolução nativa/prévia neural. Auto pode mostrar DLSS em hardware compatível. Isso não significa implementação de NVIDIA Ray Reconstruction. Durante interação a prévia prioriza fluidez; parada, refina detalhes. Editar materiais invalida a acumulação afetada; aguarde estabilizar para comparar diferenças finas.

Presets de qualidade incluem Reference, Presentation, Studio e Edit. Qualidade de luz/reflexos, método de sombra, geometria e profundidade de campo são controles distintos. Desempenho/consumo em repouso regula trabalho em segundo plano ou parado. Reduza tamanho/frequência das câmeras adicionais se suas prévias consumirem recursos.

Qualidade da viewport e qualidade offline são separadas. Aumentar amostras offline não pesa na navegação antes do render, e captura rápida não substitui amostragem offline. Escolha deliberadamente o backend de saída. Para preservar NPR no render final, use a saída deferred compatível com NPR; path tracing é outro renderizador e não deve ser presumido equivalente para efeitos de tela.

## 17 · Estilos NPR e texturas hand-painted

Escolha Qualidade da viewport > NPR e selecione o estilo. Os nomes descrevem looks, sem nomes de artistas. Projetos existentes mantêm a identidade interna do estilo após renomear. Effect enabled alterna estilos de superfície; NPR amount regula pós compatíveis. Controles variam por estilo: iluminação não deve alterar uma textura unlit.

### Unlit / Hand-painted tradicional
Atribua a textura pintada em Base color, deixe tint branco e desligue vertex color, salvo quando usado intencionalmente. Escolha Unlit / Hand-painted. Ele exibe cor pintada sem sombreamento de luzes da cena, contorno, pinceladas adicionais ou brilhos especulares. Preserve alpha intencional com Masked; escolha Opaque para modelo sólido. Serve para texturas com luzes/sombras já pintadas, por exemplo no 3DCoat. Transformação de exibição, tint e pós da cena/câmera ainda podem alterar a cor exibida.

### Catálogo de estilos
- Velvet Cel: sombreamento em faixas e limites de sombra controlados.
- Flat Cel: sombreamento simplificado e chapado.
- Layered Gouache: pintura em camadas com pinceladas e parallax.
- Bristle Paint: detalhes de pincel/altura e reflexos pintados.
- Four-Tone Canvas: paleta tonal compacta com entradas no material.
- Painted Light: resposta de iluminação pictórica.
- Living Canvas: padrões de pincel no mundo/personagem e mistura de cor.
- Illustrated Character: sombreamento ilustrativo de personagem.
- Hero Brush: tratamento gráfico de personagem com pinceladas.
- Noir Ink: tinta escura com separação de claros/escuros.
- Manga Dots: retícula monocromática.
- Pop Halftone: cores/mapas de luz, meio-tom e sombra com retícula.
- Etched Comic: impressão/hachura com exposição, saturação, contraste e brilho.
- Chromatic Print: impressão gráfica com inclusão opcional do fundo/piso.
- Graphite Study: tratamento gráfico de lápis.
- Crosshatch Shadows: hachura regulada por limiar de sombra.
- Retro Palette: divisão em grade e redução de níveis de cor.
- Pixel Mosaic: tamanho de pixel quadrado e níveis de luminância.
- Astral Shimmer: emissão nas bordas e cintilação animada sobre a cor.

### Calibrar para o assunto
Comece na resolução de saída. Espessura do contorno é em pixels; tamanho/repetição da retícula precisa combinar com o enquadramento. Pontos grandes em um personagem pequeno escondem o rosto. Compare assunto e fundo separadamente e use Incluir fundo e piso só nos estilos que oferecem a opção. Preserve cores do modelo quando desejado, em vez de paleta substituta.

Estilos de superfície podem usar direção de luz NPR que acompanha o sol da cena. Azimute/elevação e controles específicos de limiar/nitidez de sombra ajustam o look. Estilos de pós respondem à imagem renderizada da cena. Densidade, força de pincel, parallax e reflexo pintado são ajustes artísticos, não qualidade adicional de geometria.

Entradas NPR no material incluem cores/mapas de luz, meio-tom e sombra, atlas de pincel, máscaras faciais e máscara de shimmer. No atlas: RG são normais do traço, B pigmento/altura e A detalhe de cerdas. Máscaras faciais usam R frente-direita, G frente-esquerda, B trás-direita e A trás-esquerda; AO participa do limite de sombra. Um modelo genérico sem essas entradas autorais não reproduz todos os recursos de um personagem preparado especificamente.

Para renderizar, mantenha NPR ativo, escolha render final deferred ou captura direta e faça uma comparação pequena. PNG é a comparação direta de exibição. EXR linear ignora parte do processamento de exibição por definição; não o avalie sem gerenciamento de cor. Materiais de grafo especializados podem manter comportamento próprio em vez de receber todos os overrides de superfície.

## 18 · Timeline e animação

Abra Timeline por Janela ou pelo ícone do cabeçalho. Defina intervalo e FPS antes de criar um plano com duração específica. FPS relaciona quadros e tempo. Arraste o playhead para conferir um quadro; playback é prévia, não exportação offline de todos os quadros.

Selecione objeto, grupo, câmera ou controle de material animável. Adicione chaves dos valores desejados no quadro atual. Mova o playhead, altere o valor e crie a próxima chave. Use a faixa do grupo para animar um personagem com várias peças sem selecionar cada ID de material separadamente.

Interpolação define a transição entre chaves. Faixa inteira aplica a escolha à faixa completa. Use transições constantes/degrau para mudanças abruptas e suaves para movimento contínuo, conforme as opções. Confira os quadros intermediários: extremos corretos não garantem trajetória boa. A visualização do caminho ajuda a inspecionar o movimento.

Faixas de câmera animam composição e controles de lente/foco compatíveis. O override de pós da câmera é editado olhando por ela. Faixas de material usam valores publicados ou nodes Float compatíveis. Switches estáticos nativos e operações de grafo não suportadas não viram canais de timeline.

Animação importada depende do importador e dos dados. Agrupar um personagem estático não cria um rig esquelético só porque o grupo pode ser transformado. Use o programa de origem para deformações não suportadas e importe uma representação compatível.

Na saída, escolha Timeline no fluxo de render. Captura direta grava o intervalo na taxa escolhida preservando a duração. Render offline amostra quadros pelo pipeline de render. Turntable é outra tarefa, baseada no objeto/grupo e pivô selecionados; não exige criar uma chave em cada peça.

## 19 · Fluxos de render e formatos de arquivo

Abra Render e escolha o fluxo antes de pressionar o botão do cabeçalho. Saída direta usa tamanho em pixels e qualidade da vista ativa. Offline/Movie Render Queue usa resolução, câmera e amostragem configuradas. Câmera, tarefa e backend são escolhas separadas.

### Viewport direta
Escolha imagem ou gravação. Gravação ao vivo captura a navegação com os controles normais da câmera; Parar e salvar conclui. Descartar remove o temporário dessa captura, não arquivos existentes. Turntable grava uma volta dos objetos/grupo escolhidos em torno do pivô. Timeline grava o intervalo atual. Contornos de seleção e gizmos ficam ocultos na captura.

### Saída offline
Escolha câmera, largura/altura ou preset, formato e destino. Imagem estática grava uma imagem. Timeline grava o intervalo animado. Turntable executa a rotação. Use Deferred/Lumen para apresentação realtime/NPR compatível ou Path Tracing para beauty calculada fisicamente. Confira warmup de efeitos temporais antes de aumentar amostras.

PNG é imagem sem perdas e pode ter alpha quando habilitado. JPEG é compacto, com perdas e sem alpha. EXR contém dados lineares HDR/composição e exige transformação de visualização adequada. MP4 é prático para reprodução comum e não oferece transparência. GIF é leve, mas limitado em paleta, podendo apresentar banding/dither. A opção MOV com alpha se destina a composição compatível; confira o codec no programa de destino.

Use sequência de imagens quando precisar de quadros individuais ou composição robusta. Trocar a extensão não converte formato. Resolução alta, múltiplos passes e sequências longas exigem mais disco. Use uma pasta vazia e nomeada para cada versão para não misturar quadros de renders diferentes.

Depois, confira os arquivos reais: tamanho, dimensões, quantidade de quadros, primeiro/último quadro, alpha e câmera. Veja saída transparente sobre xadrez. A barra terminar não comprova que tarefa e enquadramento escolhidos eram os pretendidos.

## 20 · Qualidade offline, passes e fila de câmeras

Presets de qualidade oferecem pontos de partida Studio, Final, Reference e Path Tracing. Amostras espaciais refinam a amostragem; warmup estabiliza histórico temporal e efeitos antes de gravar. Aumentar ambos custa tempo e pode aumentar memória. Não eleve amostras para corrigir textura ou modo de opacidade atribuídos incorretamente.

Amostras por pixel do path tracing controlam convergência; bounces controlam a quantidade de interações dos raios. Poucos bounces podem mudar vidro e iluminação indireta. Intensidade máxima de firefly limita valores extremos, mas exagerar remove brilhos legítimos. O denoiser reduz ruído e pode suavizar detalhes. Compare um recorte com amostras suficientes antes de uma sequência longa.

Beauty EXR é linear. Passes deferred incluem BaseColor/DiffuseAlbedo, WorldNormal, Roughness, Metallic, Specular e Depth, além dos canais exibidos quando disponíveis. Nem todos são imagens beauty: normais são direções, depth é distância e roughness é dado escalar. Evite aplicar transformação de beauty a um passe usado para cálculo.

AOVs de componentes de luz são renders adicionais do mesmo quadro; passes de dados vêm do G-buffer. Podem elevar bastante o tempo. EXR multicamada reúne canais num contêiner compatível; arquivos separados ajudam quando o compositor não aceita esse layout. Somente beauty/preservar DOF evita passes desnecessários. Path tracing exporta beauty linear e oculta passes exclusivos do deferred.

Fila de câmeras renderiza câmeras nomeadas uma por vez em PNG, EXR ou JPEG. Use esse comando em vez de esperar que as prévias de múltiplas vistas sejam exportadas. Cancelar fila encerra e restaura a composição anterior. Confira nomes e quantidade de câmeras. Exportar vistas ortográficas gera as direções selecionadas; revise enquadramento e escala.

Para NPR, compare uma imagem e uma sequência curta na resolução desejada. Tamanho de retícula/contorno em tela pode mudar de percepção conforme a resolução. Para hand-painted, mantenha Unlit ativo e evite acrescentar sombreamento por outro renderizador.

## 21 · Preferências, atalhos e personalização

Preferências fica em Janela e no ícone de configurações. Idioma escolhe English, Português (Brasil) ou Español. Rótulos especializados de assets/controles podem permanecer na língua original. Escala, opacidade, cor da interface, contorno, sliders e texto ajustam legibilidade. Restaurar aparência volta aos padrões visuais.

Importação inclui separação de peças e cor do holograma. Alembic inclui unidades e eixo vertical. Tamanho do cubo e do gizmo ajusta auxiliares; + / − pode ajustar o gizmo quando vinculado. Ajustes de novas luzes definem valores iniciais das próximas luzes, não dispensando conferir as existentes.

Atalhos de teclado podem ser editados, limpos e restaurados. Perfis de navegação têm vínculos e comportamentos próprios. Se um atalho falhar, confira foco de entrada e vínculo antes de presumir que o comando não existe. Digitação num campo numérico não é comando de viewport.

Padrões comuns: Ctrl+N Novo; Ctrl+O Abrir; Ctrl+I Importar malha; Ctrl+S Salvar; Ctrl+Shift+S Salvar como; Ctrl+Z Desfazer; Ctrl+Shift+Z Refazer; Ctrl+R Render da tarefa atual. No grafo, Ctrl+G agrupa e Ctrl+Shift+G desagrupa. P seleciona perspectiva pelo comando View. Esc cancela escolha/desenho ativos. Vínculos personalizados podem substituir padrões; o editor de atalhos é a referência da instalação.

Favoritos reúne controles compatíveis pelo botão direito em seus rótulos. Layouts nomeados ajudam em materiais, animação e múltiplos monitores. Separe personalização da interface de presets da cena: um preset de luz/material não necessariamente restaura os painéis.

## 22 · Solução de problemas e relato de bugs

### Textura escura ou tingida
Confira Base color versus outro canal, espaço de cor, tint branco, vertex color, exposição, grading local da câmera e LUT. Use Unlit / Hand-painted para remover sombreamento da cena na comparação de textura pintada. Restaure uma categoria por vez para identificar a causa.

### Partes pretas desaparecem
Confira Opaque versus Masked/Translucent, mapa de opacidade e alpha do base color. RGB preto não é automaticamente transparente. Compare PNG RGBA sobre xadrez. Se persistir, forneça a textura original com alpha e os ajustes do material.

### Costuras UV ou relevos invertidos
Confira padding, mip/filtering, UDIM, canais e convenção de normal. Desligue vertex color para comparar só a textura. Informe estilo NPR/renderizador afetado e se a costura também aparece no arquivo renderizado.

### Navegação lenta ou path tracing não inicia
Aguarde importação e teste uma cena pequena conhecida no mesmo renderizador. Reduza tamanho/frequência das prévias extras e confira tamanho de texturas/geometria. Compare Realtime e Progressive; informe GPU, driver, VRAM e tamanho da cena. Não presuma que a GPU de outro usuário se comporte como a RTX 4060 de referência.

### Render diferente da viewport
Confirme câmera, recorte, backend, captura versus offline, pós da cena/câmera e formato. EXR linear difere de PNG de exibição. Warmup e amostras afetam efeitos temporais; inclusão do backdrop e alpha mudam o fundo. Confira arquivos reais, não apenas print da viewport.

### Controles ausentes ou seleção inesperada
Selecione o objeto/slot e renderizador corretos. Filtros podem ocultar entradas do Outliner sem esconder objetos. Câmera travada precisa ser destravada para transformar. Presets especializados expõem seus controles compatíveis. Restaure o layout se um painel estiver fora da tela; isso não exige zerar a cena.

### Relato útil
Informe versão, Windows/GPU/driver, passos exatos a partir de projeto novo ou fornecido, resultado esperado e observado, renderizador/rota de saída e uma imagem ou quadro exportado. Anexe projeto mínimo e textura necessária se tiver permissão. Inclua log relevante recente em Saved/Logs do aplicativo. Remova caminhos pessoais e dados privados sem relação antes de publicar.

Este manual documenta funções, não promete que todo shader, modelo ou codec de terceiros se comporte igualmente em todos os renders. Preserve avisos de terceiros da distribuição. Termos de compra/licença da página do produto definem assentos e uso comercial; o manual não os substitui. Use os links de suporte do download para ajuda específica da build.