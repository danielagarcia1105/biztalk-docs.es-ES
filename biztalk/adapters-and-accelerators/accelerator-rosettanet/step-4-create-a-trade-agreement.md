---
title: 'Paso 4: Crear un acuerdo comercial | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4e49efd8a2fd195c0b5fa912ced3773fa85153e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964274"
---
# <a name="step-4-create-a-trade-agreement"></a>Paso 4: Crear un acuerdo comercial
En este paso, creará un acuerdo comercial entre el inicio y la organización de socios comerciales mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.  
  
### <a name="to-create-a-trade-agreement"></a>Para crear un acuerdo comercial  
  
1.  En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda **BizTalk \<versión\> Acelerador para RosettaNet**, haga clic en **contratos**, haga clic en **New**y, a continuación, haga clic en **acuerdo**.  
  
2.  En el **nuevas propiedades de acuerdo** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **comercio acuerdo**.|  
    |**Configuración del proceso**|Seleccione **STD_0C1_R01.02** en la lista desplegable.|  
    |**Mi organización**|Seleccione **inicio** en la lista desplegable.|  
    |**Organización de socios comerciales**|Seleccione **asociado** en la lista desplegable.|  
    |**Rol principal**|Seleccione **iniciador** en la lista desplegable.|  
  
3.  En el **nuevas propiedades de acuerdo** cuadro de diálogo, en la **puertos** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de acción**|Tipo de **http://localhost/BTARNApp/RNIFReceive.aspx**.|  
    |**Dirección URL de señal**|Tipo de **http://localhost/BTARNApp/RNIFReceive.aspx**.|  
    |**Dirección URL de la sincronización**|Deje en blanco. URL de sincronización no es necesaria para el proceso de interfaz de socio (PIP) sincrónico.|  
  
4.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
 Después de crear el acuerdo comercial, primero debe activarlo.  
  
### <a name="to-activate-the-trade-agreement"></a>Para activar el acuerdo comercial  
  
-   En el [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **contratos**, haga clic en **acuerdo comercial** en el panel de resultados y, a continuación, haga clic en **activar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 5: Crear un acuerdo reflejado](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)