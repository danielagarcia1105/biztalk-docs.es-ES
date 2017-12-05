---
title: Herramienta de MllpReceive | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e990c49a221653289619a33c30100accc3c68d6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="mllpreceive-tool"></a>Herramienta MllpReceive
Puede utilizar la herramienta MllpReceive para recibir datos de un puerto de envío MLLP.  
  
 Instalar esta herramienta a través de la [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] procedimiento de instalación personalizada. Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba en orden para que funcione correctamente este tutorial. En la pantalla instalación personalizada, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **instancias de prueba** desde el **artefactos** carpeta. Para obtener más información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).  
  
 El programa de instalación de BTAHL7 instala esta herramienta en  *\<unidad\>*: \Program BizTalk \<versión\> Acelerador para HL7\SDK\MLLP utilidades.  
  
 Use esta herramienta en el [-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), el [Tutorial Interrogative](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), el [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)y el [mensaje enriquecimiento Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). Si ha instalado [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] a través de la instalación predeterminada y no se ha instalado la herramienta MLLPTest (incluidos MllpReceive y MllpSend), no podrá probar los resultados del tutoriales.  
  
## <a name="tool-usage"></a>Uso de la herramienta  
 A continuación muestra la sintaxis usada para invocar esta herramienta de línea de comandos:  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 En la tabla siguiente describe cada parte de la sintaxis que se utiliza la herramienta MllpReceive.  
  
|Sintaxis|Significado|  
|------------|-------------|  
|/?|Muestra esta Ayuda.|  
|/I \<IP\>|Indica la dirección para escuchar. El valor predeterminado es direcciones IP disponible.|  
|/P \<PUERTO\>|Indica el número de puerto para escuchar. El valor predeterminado es 12000.|  
|/D \<DIRECTORY\>|Almacena recibidos todos los mensajes en el directorio \<DIRECTORY\>. Si no se especifica \<directorio\>, el directorio predeterminado es % TEMP %.|  
|/ DIVISIÓN|Divide los datos recibidos en mensajes independientes en función de los delimitadores. Se requiere SB y EB. CR es opcional.|  
|/ STATICACK|La confirmación estática que se devuelve al remitente. Aplicará el modo de división.|  
|/ HL7ACK|La confirmación de HL7 devuelve al remitente. Nombre de archivo indica el nombre del archivo que contiene la confirmación HL7. Aplicará el modo de división.|  
|/ SB|Establece el valor ASCII de bytes de delimitador de bloque de inicio. El valor predeterminado es none.|  
|/EB|Establece el valor ASCII de bytes de delimitador de bloque final. El valor predeterminado es none.|  
|/CR|Establece el valor ASCII de bytes de transporte devolver delimitador. El valor predeterminado es none.|  
  
## <a name="example-of-tool-use"></a>Ejemplo de uso de herramienta  
 Puede usar el siguiente comando para escuchar al puerto 10000 en localhost y guardar mensajes para separar archivos en C:\TEMP:  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)