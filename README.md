# RecyclerItemClickListener

## Passo a passo para criar um evento de clique do componente de listagem recyclerView

- Criar a classe RecyclerItemClickListener no pacote principal do java 
- Criar o método recyclerView.addOnItemTouchListener(); no MainActivity.java

```bash
//evento de clique
        recyclerView.addOnItemTouchListener(
            new RecyclerItemClickListener(
                    getApplicationContext(),
                    recyclerView,
                    new RecyclerItemClickListener.OnItemClickListener() {
                        @Override
                        public void onItemClick(View view, int position) {
                            Filme filme = listaFilmes.get(position);
                            Toast.makeText(getApplicationContext(),
                                    "Item pressionado: " + filme.getTitulo(),
                                    Toast.LENGTH_SHORT)
                                    .show();
                        }

                        @Override
                        public void onLongItemClick(View view, int position) {
                            Filme filme = listaFilmes.get(position); // objeto criado
                            Toast.makeText(getApplicationContext(),
                                    "Clique longo: " + filme.getTitulo(),
                                    Toast.LENGTH_SHORT)
                                    .show();
                        }

                        @Override
                        public void onItemClick(AdapterView<?> parent, View view, int position, long id) {

                        }
                    }
            )
        );
