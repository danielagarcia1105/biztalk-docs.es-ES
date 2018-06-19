---
title: Requisitos previos para el tutorial de doble acción de RosettaNet en BizTalk Server | Documentos de Microsoft
description: Requisitos previos para recorrer el tutorial de doble acción para el Acelerador para RosettaNet (BTARN) en BizTalk Server
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
ms.openlocfilehash: cfc247aa1ab9ec7cb6f056cd45df54bc324990ad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963522"
---
# <a name="prepare-for-the-double-action-tutorial"></a>Prepararse para el tutorial de doble acción

## <a name="prerequisites"></a>Requisitos previos
Antes de iniciar el tutorial:
  
-   Realice una instalación completa de BizTalk Server y [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] en dos equipos. Para obtener más información, consulte [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).  
  
    > [!IMPORTANT]
    >  Asegúrese de configurar totalmente el Acelerador para RosettaNet, incluido el inicio de las orquestaciones de BTARN. Vea [instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md).
  
-   Este tutorial simula un escenario real mediante el uso de dos equipos en lugar de un único equipo con un contrato de bucle invertido. Cada vez que este tutorial usa nombres de equipo, utiliza un marcador de posición. Reemplace ese marcador de posición con el nombre real del equipo elegido. Por ejemplo, si el equipo que está ejecutando la solución de Contoso se denomina **Contoso**, reemplace las apariciones en el tutorial de \\ \\< contoso **_**  *equipo* \> con ese nombre de equipo.  
  
-   Este tutorial promueve una comunicación segura a través de certificados entre Contoso y Fabrikam. Debe generar los certificados que requiere e instalarlas en sus respectivos equipos.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Paso 1: Crear una entidad de certificación](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [Paso 2: Crear certificados públicos y privados](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [Paso 3: Importar certificados públicos y privados](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [Paso 4: Habilitar Capa de sockets seguros en IIS](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)