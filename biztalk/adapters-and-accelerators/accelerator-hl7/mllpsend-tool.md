---
title: Herramienta de MllpSend | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a15da306f61cb4297d9ba8cdc036035310474d8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="mllpsend-tool"></a>Herramienta MllpSend
Puede utilizar la herramienta MllpSend para enviar datos a un MLLP la ubicación de recepción.  
  
 Instalar esta herramienta a través de la [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] procedimiento de instalación personalizada. Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba en orden para que funcione correctamente este tutorial. En la pantalla instalación personalizada, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **instancias de prueba** desde el **artefactos** carpeta. Para obtener más información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).  
  
 El programa de instalación de BTAHL7 instala esta herramienta en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for HL7\SDK\MLLP utilidades.  
  
 Use esta herramienta en el [-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), el [Tutorial Interrogative](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), el [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)y el [mensaje enriquecimiento Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). Si ha instalado [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] a través de la instalación predeterminada y no se ha instalado el Testtools MLLP (incluidos MllpSend y MllpReceive), no podrá probar los resultados del tutoriales.  
  
## <a name="tool-usage"></a>Uso de la herramienta  
 A continuación muestra la sintaxis usada para invocar esta herramienta de línea de comandos:  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 En la tabla siguiente describe cada parte de la sintaxis que se utiliza la herramienta MllpSend.  
  
|Sintaxis|Description|  
|------------|-----------------|  
|**/?**|Muestra la Ayuda en la ventana de símbolo del sistema.|  
|**/I \<IP >**|Indica la dirección que se envía a. El valor predeterminado es localhost.|  
|**/P \<PUERTO >**|Indica el número de puerto para enviar a. El valor predeterminado es **11000**.|  
|**/F**|Envía el contenido del archivo de nombre de archivo.|  
|**/ REPETICIÓN\<n>**|Envía el mismo mensaje  *n*  veces. Los caracteres de contenedor se aplicarán a cada mensaje.|  
|**/ TWOWAY**|El remitente va a esperar una respuesta desde el receptor. SB y EB deben especificarse. CR es opcional. En el modo de archivo, la respuesta se almacena en el archivo. RESPUESTA.|  
|**/ SB**|Establece el valor ASCII del Byte de delimitador de bloque de inicio. El valor predeterminado es none.|  
|**/EB**|Establece el valor ASCII del Byte de delimitador de bloque final. El valor predeterminado es none.|  
|**/CR**|Establece el valor ASCII del carro devolver delimitador Byte. El valor predeterminado es none.|  
  
## <a name="examples-of-tool-use"></a>Ejemplos de uso de herramienta  
 Los ejemplos siguientes muestran cómo puede utilizar la herramienta MllpSend.  
  
 **Ejemplo 1.** Puede utilizar el siguiente comando para enviar un mensaje a un adaptador unidireccional escuchando en el puerto 13000 servidor "myserver". Los valores ASCII de los caracteres de contenedor son SB 11, EB 28 y CR 13.  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 **Ejemplo 2.** Puede utilizar el siguiente comando para enviar un mensaje de 100 veces a un adaptador bidireccional escuchando en el puerto 11000 servidor "localhost". Los valores ASCII de los caracteres de contenedor son SB 11, EB 28 y CR 13.  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)