---
title: Instalar el Software necesario, utilidades y ejemplos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f92f4cc994b4139c1c33423cc7a94c9072e226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965909"
---
# <a name="install-the-required-software-utilities-and-samples"></a>Instalar el Software necesario, utilidades y ejemplos
Este tutorial requiere Microsoft Windows Server y Microsoft personalizado [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] instalación que incluye las herramientas de prueba de MLLP. Además, debe estar familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desarrollo en Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] y [Obtenga información sobre el Acelerador de HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).
  
 Debe tener las siguientes utilidades y ejemplos instalados en el equipo:  
  
- **Herramienta MllpSend**  
  
   Esta utilidad de línea de comandos envía un mensaje a través el protocolo de capa inferior (MLLP) mínima ubicación de recepción de protocolo para una MLLP. Usarlo para probar los resultados del tutoriales. Para obtener más información, consulte [herramienta MllpSend](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).  
  
- **Herramienta MllpPReceive**  
  
   Esta utilidad de línea de comandos recibe mensajes a través del protocolo MLLP, que actúa como un agente de escucha de la ubicación de recepción. Usa para probar los resultados del tutoriales, la presentación de mensajes y las confirmaciones recibidas. Para obtener más información, consulte [herramienta MllpReceive](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).  
  
- **Aplicación de ejemplo acepta ACK.txt**  
  
   Este archivo de ejemplo contiene el texto de un mensaje de confirmación de aceptación de aplicación. El ejemplo funciona con la herramienta MllpReceive, que recibe y muestra los mensajes y, a continuación, envía las confirmaciones de vuelta en el archivo de ejemplo.  
  
  Deberá instalar las dos herramientas y el archivo de ejemplo mediante el proceso de instalación de BTAHL7 personalizado. El proceso de instalación típica no instala estas herramientas. Para instalar estas herramientas, ejecute la instalación personalizada de BTAHL7, en el **instalación personalizada** pantalla, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **Las instancias de prueba** desde el **artefactos** carpeta. Para obtener más información, consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).  
  
## <a name="see-also"></a>Vea también  
 [Preparación para usar el tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)