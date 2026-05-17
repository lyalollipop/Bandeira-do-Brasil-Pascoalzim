program BandeiraDoBrasil;
uses graph;

var
  gd, gm: integer;

begin
  gd := detect;
  InitGraph(gd, gm, '');

  { --- RETÂNGULO VERDE --- }
  SetFillStyle(SolidFill, Green);
  SetColor(Green);
  Bar(50, 50, 750, 450);


  { --- LOSANGO AMARELO --- }
  { 1. Definimos a cor da linha como Amarelo }
  SetColor(Yellow);
  
  { 2. Desenhamos as 4 linhas do contorno do losango }
  Line(400, 80,  710, 250); { Topo para a Direita }
  Line(710, 250, 400, 420); { Direita para Baixo }
  Line(400, 420, 90,  250); { Baixo para a Esquerda }
  Line(90,  250, 400, 80);  { Esquerda para o Topo }
  
  { 3. Pintamos o interior do losango }
  SetFillStyle(SolidFill, Yellow);
  { O FloodFill pinta a partir de um ponto interno (400,250 é o centro) }
  { até encontrar a borda da cor indicada (Yellow) }
  FloodFill(400, 250, Yellow);


  { --- CÍRCULO AZUL --- }
  SetFillStyle(SolidFill, Blue);
  SetColor(Blue);
  FillEllipse(400, 250, 95, 95);


  { --- FAIXA BRANCA --- }
  SetColor(White);
  Line(310, 270, 490, 225);


  { Mensagem de saída }
  SetColor(White);
  OutTextXY(50, 465, 'Pressione Enter para sair...');
  
  Readln;
  CloseGraph;
end.
