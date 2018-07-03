---
title: Requisitos previos del tutorial de procesos privados de RosettaNet en BizTalk Server | Microsoft Docs
description: Requisitos previos para recorrer el tutorial de procesos privados para el Acelerador de RosettaNet (BTARN) en BizTalk Server
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 823788385b659f5aa26d4aa92db1e234f2773600
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010933"
---
# <a name="prepare-for-the-private-process-tutorial"></a>Prepararse para el tutorial de procesos privados

## <a name="prerequisites"></a>Requisitos previos
Antes de comenzar el tutorial:
  
- Realizar una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos. Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).  
  
  > [!IMPORTANT]
  >  Asegúrese de que configurar completamente el Acelerador de RosettaNet, incluido el inicio de las orquestaciones de BTARN. Consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md). También es posible que deba agregar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] directorios virtuales (incluidos btarnhttpreceive) a la lista de exclusión de ruta de acceso administrada de Microsoft Windows® SharePoint™ Services. 
  
- Este tutorial simula un escenario del mundo real con dos equipos en lugar de un solo equipo con un acuerdo de bucle invertido. Cada vez que este tutorial usa los nombres de equipo, utiliza un marcador de posición como el nombre del equipo. Reemplace el marcador de posición con el nombre real del equipo que eligió. Por ejemplo, si el equipo que ejecuta la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso<strong>_</strong>  *equipo* \> con ese nombre de equipo.  
  
  En este tutorial se promueve una comunicación segura a través de certificados entre Contoso y Fabrikam. Debe generar los certificados que requiere e instalarlos en los respectivos equipos.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Restauración de la base de datos de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [Generación y habilitación de certificados](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)