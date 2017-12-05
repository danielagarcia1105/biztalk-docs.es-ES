---
title: Requisitos previos para el tutorial de procesos de RosettaNet privados en BizTalk Server | Documentos de Microsoft
description: Requisitos previos para recorrer el tutorial de procesos privados para el Acelerador para RosettaNet (BTARN) en BizTalk Server
caps.latest.revision: "7"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 580edcc7a8d779067895fb5aac99d81a1ad76872
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="prepare-for-the-private-process-tutorial"></a>Prepararse para el tutorial de procesos privado

## <a name="prerequisites"></a>Requisitos previos
Antes de iniciar el tutorial:
  
-   Realice una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos. Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).  
  
    > [!IMPORTANT]
    >  Asegúrese de configurar totalmente el Acelerador para RosettaNet, incluido el inicio de las orquestaciones de BTARN. Vea [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md). También es podrán que deba agregar la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] directorios virtuales (incluidos los btarnhttpreceive) a la lista de exclusión de la ruta de acceso administrado de Microsoft Windows® SharePoint™ Services. 
  
-   Este tutorial simula un escenario real mediante el uso de dos equipos en lugar de un único equipo con un contrato de bucle invertido. Cada vez que este tutorial usa nombres de equipo, utiliza un marcador de posición como el nombre del equipo. Reemplace ese marcador de posición con el nombre real del equipo elegido. Por ejemplo, si el equipo que está ejecutando la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso**_**  *equipo* \> con ese nombre de equipo.  
  
 Este tutorial promueve una comunicación segura a través de certificados entre Contoso y Fabrikam. Debe generar los certificados que requiere e instalarlos en los equipos correspondientes.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Restauración de la base de datos de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [Generación y habilitación de certificados](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)