---
title: 'Paso 5: Crear los intercambios de Fabrikam 3A2 contrato de socios | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating agreements
ms.assetid: a5fafdc6-e9dd-4d15-98a2-8b603901308c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e945223013e80c4f0550a388cbc0811861846ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-creating-the-fabrikam-3a2-trading-partner-agreement"></a>Paso 5: Crear el acuerdo de socio comercial Fabrikam 3A2
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo de socio comercial para el proceso de interfaz de socio (PIP) 3A2.  
  
### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  
  
-   Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for RosettaNet**y, a continuación, haga clic en  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Consola de administración.  
  
### <a name="to-create-the-3a2-trading-partner-agreement"></a>Para crear el acuerdo de socio comercial de 3A2  
  
1.  En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo** .  
  
2.  En el **nuevas propiedades de acuerdo** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Fabrikam_To_Contoso_3A2**.|  
    |**Configuración del proceso**|Seleccione **STD_3A2_R02.00.00A** en la lista desplegable.|  
    |**Mi organización**|Seleccione **Fabrikam** en la lista desplegable.|  
    |**Organización de socios comerciales**|Seleccione **Contoso** en la lista desplegable.|  
    |**Versión RNIF**|Seleccione **V02.00.01** en la lista desplegable.|  
    |**Rol principal**|Seleccione **cliente (iniciador)** en la lista desplegable.|  
    |**Uso**|Seleccione **Prueba** en la lista desplegable.|  
  
3.  Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de acción**|Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.|  
    |**Dirección URL de señal**|Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.|  
    |**Dirección URL de la sincronización**|Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.|  
  
4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en el **Fabrikam_To_Contoso_3A2** acuerdo y, a continuación, haga clic en **activar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 6: Crear el acuerdo de socio comercial Fabrikam 3A4](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)