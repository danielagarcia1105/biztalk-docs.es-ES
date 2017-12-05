---
title: 'Paso 3: Crear el acuerdo de socios comerciales 2 de Fabrikam 0c | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating agreements
ms.assetid: 4552f712-f226-423f-b06d-98e943e8efd4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 746256a744a5d89f325ccaecb7d71185383f8efd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-creating-the-fabrikam-0c2-trading-partner-agreement"></a>Paso 3: Crear el acuerdo de socio comercial Fabrikam 0c comerciales 2
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo de socio comercial para el 0c 2 proceso de interfaz de socio (PIP).  
  
### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  
  
-   Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Consola de administración.  
  
### <a name="to-create-the-0c2-trading-partner-agreement"></a>Para crear el 0c de contrato de socios comerciales de 2  
  
1.  En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo** .  
  
2.  En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Fabrikam_To_Contoso_0C2**.|  
    |**Configuración del proceso**|Seleccione **STD_0C2_R01.02** en la lista desplegable.|  
    |**Mi organización**|Seleccione **Fabrikam** en la lista desplegable.|  
    |**Organización de socios comerciales**|Seleccione **Contoso** en la lista desplegable.|  
    |**Versión RNIF**|Seleccione **V02.00.01** en la lista desplegable.|  
    |**Rol principal**|Seleccione **iniciador (iniciador)** en la lista desplegable.|  
    |**Uso**|Seleccione **Prueba** en la lista desplegable.|  
  
3.  Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de acción**|Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.|  
    |**Dirección URL de señal**|Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.|  
    |**Dirección URL de la sincronización**|Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.|  
  
4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en el **Fabrikam_To_Contoso_0C2** acuerdo y, a continuación, haga clic en **activar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Creación del acuerdo entre socios comerciales Fabrikam 0C4](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)