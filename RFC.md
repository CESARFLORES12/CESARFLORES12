#include <iostream>
#include <string>

//funcion para obtener la primera vocal interna
char obtenerPrimeraVocalInterna(const std::string& str){
    for (size_t i = 1; i < str.length(); ++i){
        char c = str[i];
        if ( c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U')
        return c;
    }
    return 'X';//si no se encuentra ninguna vocal interna, entonces se utiliza x
}

std::string calcularRFC(const std::string& nombre, const std::string& apellidoPaterno, const std::string& apellidoMaterno, const std::string& fechaNac){
        std::string rfc;
        
    char letrainicial = apellidoPaterno[0];
    char primervocalinterna = obtenerPrimeraVocalInterna(apellidoPaterno);
    //Si no cuenta con un apellido se mostrara la x
    char inicialapellidoMaterno = (!apellidoMaterno.empty()) ? apellidoMaterno[0] : 'X';
    
     char inicialnombre=nombre[0];
     
     std::string anio = fechaNac.substr(2,2);
      std::string mes = fechaNac.substr(5,2);
      std::string dia = fechaNac.substr(8,2);
      
      rfc = letrainicial;
      rfc += primervocalinterna;
      rfc +=inicialapellidoMaterno;
     rfc +=inicialnombre;
     rfc +=anio;
     rfc +=mes;
     rfc +=dia;
     return rfc;
     
    
} 
