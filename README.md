#  Devoir : le Challenge des paramètres
### Voici le programme :
```
#include <iostream>
#include <vector>
#include <new>
#include <stdexcept>

using namespace std;

void Fonction_limits(const vector<int> & parametre){
    cout << "Nombre de parametres est : " << parametre.size() <<endl;
    }


int main() {
    try{
      for(size_t i=1 ; ; i*=3){
        vector<int> parametre(i,1);
        Fonction_limits(parametre);
      }
    }catch(const bad_alloc & e){
       cout << "L'erreur est : " << e.what() <<endl;
    }
     return 0;
}
```
### Le résultat de ce programme est :
<img src="https://github.com/user-attachments/assets/1ee32d2e-933d-4e5a-b4ff-e53cc7252387" width="800px">

#### Le résultat obtenu montre le nombre maximal de paramètres qu'une fonction peut accepter pour mon compilateur GNU GCC :
<img src="https://github.com/user-attachments/assets/5261643b-5810-44b6-bfa0-8e636cdebde3" width="500px">

#### avant de provoquer une exception de type ```std::bad_alloc```, ce qui signifie que le programme a essayé d'allouer de la mémoire, mais que la mémoire disponible a été épuisée sur le heap. Donc, le nombre maximale de parametres peuvent accepte par une fonction dépend de l'architecture de la machine (RAM disponible, gestion du heap, espace d'adressage sur le systeme 64 bits) et de la gestion de la mémoire par le système d'exploitation. Lorsque cette mémoire est épuisée, l'exception est levée, comme observé dans les résultats.
