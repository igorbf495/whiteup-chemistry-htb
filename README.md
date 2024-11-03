# whiteup-chemistry-htb


alvo: 10.10.11.38

primeiro vamo começar fazendo um reconhecimento, apra procurar por portas aberta nesse ip.

![image](https://github.com/user-attachments/assets/5387a6bb-ed77-4f63-847a-272016f3d149)

vimos que tem dois serviços rodando, ssh na porta padrão e a porta 5000, vou tentar acessar essa porta 5000 na web

![image](https://github.com/user-attachments/assets/1cb50d91-f52a-4a77-9ac0-64c86b513c07)

encontramos esse CIF Analyzer, não o que é então fui dar uma pesquisada, parece que é um sistema que extrai informações de ligação de arquivos de informações cristalográficas (CIF), vou clicar em register para me registrar e conheçer melhor a aplicação

![image](https://github.com/user-attachments/assets/6a239045-965c-4a11-968c-a715cf738196)

aqui vemos que da pra fazer um upload de arquivo CIF válido

cliquei em here para ele baixar esse example.cif para eu tentar entender melhor como funciona esse cif

![image](https://github.com/user-attachments/assets/efc43522-18c4-4d94-aee7-d6f6f072ece1)

analisei e mesmo assim não sai do lugar, mas vi que CIF significa Crystallographic Information Files, vou pesquisar se existe algum cve desse tipo de arquivo


![image](https://github.com/user-attachments/assets/e679f90e-0e15-4e51-9489-8289367f2264)


depois de um bom tempo de pesquisa, encontrei algo interessante no CVE-2024-23346 que se refere à uma vulnerabilidade crítica no pymatgen, uma biblioteca Python de código aberto utilizada para análise de materiais. 

https://ethicalhacking.uk/cve-2024-23346-arbitrary-code-execution-in-pymatgen-via-insecure/#gsc.tab=0

aqui encontrei o seguinte exploit:

![image](https://github.com/user-attachments/assets/87b92bb3-3eed-4849-bc76-7bae66852a49)

fui pesquisar mais sobre essa vulnerabilidade desta lib pymatgen e encontrei o seguinte exploit no github:

https://github.com/materialsproject/pymatgen/security/advisories/GHSA-vgv8-5cpj-qj2f

![image](https://github.com/user-attachments/assets/7c57f734-fabb-4950-babb-a732539724cc)



