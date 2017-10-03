---
title: Instalar el Software necesario, utilidades y ejemplos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 678037cd050ae8375b3c9ec465860d939d48cccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-required-software-utilities-and-samples"></a>Instalar el Software necesario, utilidades y ejemplos
Este tutorial requiere [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Windows Server y un personalizado [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] instalación que incluye las herramientas de prueba de MLLP. Además, debe estar familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desarrollo en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] y [obtener información sobre el Acelerador para HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).
  
 Debe tener las siguientes utilidades y ejemplos instalados en el equipo:  
  
-   **Herramienta MllpSend**  
  
     Esta utilidad de línea de comandos envía un mensaje sobre el protocolo de capa inferior (MLLP) mínimo protocolo a un MLLP ubicación de recepción. Se usa para comprobar los resultados del tutoriales. Para obtener más información, consulte [MllpSend herramienta](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).  
  
-   **Herramienta MllpPReceive**  
  
     Esta utilidad de línea de comandos recibe mensajes a través del protocolo MLLP, que actúa como un agente de escucha de la ubicación de recepción. Se usa para comprobar los resultados del tutoriales, presentación de mensajes y confirmaciones recibidas. Para obtener más información, consulte [MllpReceive herramienta](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).  
  
-   **Aplicación de ejemplo acepta ACK.txt**  
  
     Este archivo de ejemplo contiene el texto de un mensaje de confirmación de aceptación de aplicación. El ejemplo funciona con la herramienta MllpReceive, que recibe y muestra los mensajes y, a continuación, devuelve las confirmaciones en el archivo de ejemplo.  
  
 Debe instalar las dos herramientas y el archivo de ejemplo mediante el proceso de instalación de BTAHL7 personalizado. El proceso de instalación típica no instala estas herramientas. Para instalar estas herramientas, ejecute la instalación personalizada de BTAHL7, en la **personalizada** pantalla, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **Instancias de prueba** desde el **artefactos** carpeta. Para obtener más información, consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).  
  
## <a name="see-also"></a>Vea también  
 [Preparando para utilizar el Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)