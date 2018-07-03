---
title: FlatFileSend (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52dd0018-e272-40db-a26a-509d444d7106
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 471f49c7bae30a032d50e474b80efbf12d2ffdd2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000749"
---
# <a name="flatfilesend-biztalk-server-sample"></a>FlatFileSend (ejemplo de BizTalk Server)
El ejemplo FlatFileSend muestra cómo puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para procesar un archivo XML en el archivo sin formato equivalente.  

## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo configura la carpeta FFInput como ubicación de recepción. Cuando se coloca un archivo, como el archivo de ejemplo FlatFileSend_in.xml, en esta carpeta, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa el mensaje de este archivo mediante los siguientes pasos:  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lee el mensaje del archivo de entrada en la carpeta FFInput de la ubicación de recepción.  

2. El mensaje pasa a través de una canalización de recepción XML.  

3. En la base de datos de cuadro de mensajes, el mensaje se enruta a un puerto de envío de archivos que tiene una canalización de envío configurada con un componente Ensamblador de archivo sin formato. El componente Ensamblador de archivo sin formato convierte el mensaje XML en una representación de archivo sin formato equivalente mediante un esquema de archivo sin formato.  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escribe el mensaje convertido en un archivo de texto en la carpeta FFOutput del adaptador de envío.  

## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El mensaje de ejemplo determina la mayor parte del diseño básico de este ejemplo. Los mensajes de archivos sin formato se deben ensamblar con el Ensamblador de archivo sin formato y un esquema de archivo sin formato en la canalización de envío personalizada. Estos y otros elementos de diseño se resumen en la siguiente tabla.  


|    Elemento de diseño    |                                                                                                                                                                    Razones seleccionadas                                                                                                                                                                    |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Canalización de envío personalizada | -La canalización personalizada utiliza el ensamblador de archivo sin formato y un esquema de archivo sin formato para traducir los mensajes de instancia en el formato de archivo sin formato; el ensamblador de archivo sin formato no es una canalización y no se puede usar al configurar una canalización de envío en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. |
|   Esquema de archivos sin formato   |                                      -Definen todas las mismas características registros y campos (incluida la estructura) como un esquema XML y proporciona un mecanismo para definir todas las características de archivo sin formato que se necesitan para traducir un mensaje de instancia XML en un mensaje de archivo sin formato (o viceversa).                                      |
| Filtro de suscripción  |                                                                                                          -El filtro de suscripción realiza el enrutamiento real mediante la captura de mensajes que cumplen los criterios de uno o varios basados en campos de propiedades.                                                                                                          |
|      XMLReceive      |                                                                                                        -Realiza un procesamiento de mensajes XML entrantes. Para este ejemplo se utiliza una representación XML de un pedido de compra como mensaje de origen.                                                                                                        |

 Estos elementos se combinan para producir una solución que acepta mensajes de pedido de compra en formato XML en la ubicación de recepción y escribe un pedido de compra de archivo sin formato en la ubicación de envío.  

## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de la ruta de acceso\>* \Pipelines\AssemblerDisassembler\FlatFileSend  

 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  


|                Archivos                |                                                                                           Descripción                                                                                            |
|---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Cleanup.bat              | Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global. Quita los puertos de envío y recepción. Quita los directorios virtuales de los Servicios de Microsoft Internet Information (IIS) según sea necesario. |
| FlatFileSend.btproj, FlatFileSend.sln |                                                                           Archivos de proyectos y de soluciones de este ejemplo.                                                                            |
|        FlatFileSendBinding.xml        |                                                                          Se usa para la instalación automatizada, como el enlace de puerto.                                                                          |
|          FlatFileSend_in.xml          |                                                                                        Archivo de entrada de ejemplo.                                                                                        |
|                PO.xsd                 |                                                                                  Esquema del archivo sin formato saliente.                                                                                  |
|           SendPipeline.btp            |                          Archivo de canalización de envío de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con el componente Ensamblador de archivo sin formato.                           |
|               Setup.bat               |                                                                            Se utiliza para crear e iniciar este ejemplo.                                                                             |

## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Use este ejemplo como base para su propia solución de procesamiento de archivos sin formato. Puede ampliar muchos de los elementos de diseño usados en este ejemplo para cumplir sus propios requisitos.  

## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  

1. En una ventana de comandos, desplácese a la siguiente carpeta:  

    *\<Ejemplos de la ruta de acceso\>* \Pipelines\AssemblerDisassembler\FlatFileSend  

2. Ejecute el archivo Setup.bat que realiza las acciones siguientes:  

   - Crea la carpeta de entrada (FFInput) y la carpeta de salida (FFOutput) para este ejemplo en la carpeta:  

      *\<Ejemplos de la ruta de acceso\>* \Pipelines\AssemblerDisassembler\FlatFileSend  

   - Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  

   - Crea y enlaza la ubicación de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los puertos de envío y recepción.  

     > [!NOTE]
     >  Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos: `Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.` puede ignorar estas advertencias. (Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).  

   - Habilita la ubicación de recepción e inicia el puerto de envío.  

> [!NOTE]
>  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
> 
> [!NOTE]
>  Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar el ensamblado resultante.  
> 
> [!NOTE]
>  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  

## <a name="running-this-sample"></a>Ejecución del ejemplo  

1.  Guarde una copia del archivo FlatFileSend_in.xml en la carpeta FFInput.  

2.  Observe el archivo de texto creado en la carpeta FFOutput. El nombre del archivo de texto se basa en el GUID de Id. del mensaje. Este archivo contiene el equivalente de archivo sin formato del archivo de entrada XML FlatFileSend_in.xml.  

## <a name="classes-or-methods-used-in-this-sample"></a>Clases o métodos usados en el ejemplo  
 Las secuencias de comandos de configuración Setup.bat y Cleanup.bat se basan en las siguientes secuencias de comando administrativas del instrumental de administración de Windows (WMI):  

- Iniciar puerto de envío\StartSendPort.vbs  

- Habilitar ubicación de recepción\EnableRecLoc  

- Quitar puerto de envío\RemoveSendPort  

  Los archivos por lotes de instalación y de limpieza usan BTSTask de la siguiente forma:  

- **BTSTask ImportBindings** para aplicar el archivo de enlace y crear la aplicación, puertos y enlaces  

- **BTSTask RemoveApp** para quitar flatfilesendapplication.  

## <a name="see-also"></a>Vea también  
- [Esquemas de archivos sin formato](../core/flat-file-schemas.md)   
- [Canalizaciones predeterminadas](../core/default-pipelines.md)   
- [Pipelines\AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
- **Ejemplos de scripts de WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)   
- [FlatFileReceive (ejemplo de BizTalk Server)](../core/flatfilereceive-biztalk-server-sample.md)
