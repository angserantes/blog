# Creación de una página en Symphony

1. Se crea un controlador en el proyecto de la librería de Symphony llamado Blog con el que ya veníamos trabajando.

2. Para hacerlo se crea una clase "controlador" y ubn método "controlador" dentro de ella:
   
   <?php
// src/Controller/LuckyController.php
namespace App\Controller;

use Symfony\Component\HttpFoundation\Response;

class LuckyController
{
    public function number(): Response
    {
        $number = random_int(0, 100);

        return new Response(
            '<html><body>Lucky number: '.$number.'</body></html>'
        );
    }
}

3. Para enlazar la ruta con el controlador:  en el archivo routes.yaml añadimos:

index:
    path: /
    controller: App\Controller\LuckyController::number

