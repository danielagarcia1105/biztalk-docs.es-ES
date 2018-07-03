---
title: Requisitos previos del tutorial de doble acción de RosettaNet en BizTalk Server | Microsoft Docs
description: Requisitos previos para recorrer el tutorial de doble acción para el Acelerador de RosettaNet (BTARN) en BizTalk Server
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48584cf7dfee0ca4812b41e56b4e8f7c0984e4fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979013"
---
# <a name="prepare-for-the-double-action-tutorial"></a>Prepararse para el tutorial de doble acción

## <a name="prerequisites"></a>Requisitos previos
Antes de comenzar el tutorial:
  
- Realizar una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos. Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).  
  
  > [!IMPORTANT]
  >  Asegúrese de que configurar completamente el Acelerador de RosettaNet, incluido el inicio de las orquestaciones de BTARN. Consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).
  
- Este tutorial simula un escenario del mundo real con dos equipos en lugar de un solo equipo con un acuerdo de bucle invertido. Cada vez que este tutorial usa los nombres de equipo, utiliza un marcador de posición. Reemplace el marcador de posición con el nombre real del equipo que eligió. Por ejemplo, si el equipo que ejecuta la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso<strong>_</strong>  *equipo* \> con ese nombre de equipo.  
  
- En este tutorial se promueve una comunicación segura a través de certificados entre Contoso y Fabrikam. Debe generar los certificados que requiere e instalarlas en sus respectivos equipos.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Paso 1: Crear una entidad de certificación](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [Paso 2: Crear certificados públicos y privados](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [Paso 3: Importar certificados públicos y privados](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [Paso 4: Habilitar Capa de sockets seguros en IIS](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)