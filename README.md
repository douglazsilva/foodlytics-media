# foodlytics-media

Bucket público de imagens usado pelo publicador do Instagram do projeto
[foodlytics](https://github.com/douglazsilva/foodlytics).

## Por que este repo existe

A Content Publishing API do Instagram não aceita upload de arquivo: ela **baixa
a imagem por URL pública**. As fotos do projeto ficam num repo privado, então
cada publicação sobe a imagem aqui primeiro e passa a URL
`raw.githubusercontent.com` para a Meta.

## Como é usado

Nada aqui é editado à mão. O publicador envia `posts/<id>.jpg` via API do GitHub
antes de cada publicação:

```
posts/story-20261025-combo.jpg
posts/carrossel-20261025-promo-1.jpg
posts/carrossel-20261025-promo-2.jpg
```

O nome vem do `id` do item na fila (mais `-1`, `-2`, ... no caso de carrossel).
Arquivos antigos podem ser apagados sem impacto — a publicação já aconteceu.

## Regras

- Este repo precisa continuar **público**: `raw.githubusercontent.com` não serve
  arquivo de repo privado.
- Não coloque segredos, tokens ou dados de clientes aqui.
- Não edite/renomeie arquivos manualmente; o publicador assume que a URL é
  estável entre criar o container e publicar.
