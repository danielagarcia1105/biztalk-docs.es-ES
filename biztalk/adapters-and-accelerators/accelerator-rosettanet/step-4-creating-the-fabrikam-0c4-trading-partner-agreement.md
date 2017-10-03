---
title: 'Paso 4: Crear el acuerdo de socios comerciales 4 de Fabrikam 0c | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating agreements
ms.assetid: a99c2cd1-0d42-4fae-a380-a53d77cd87d0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d42e35512067f62d19b9aa6fc203e683890d6a3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-creating-the-fabrikam-0c4-trading-partner-agreement"></a>Paso 4: Crear el acuerdo de socios comerciales 4 de Fabrikam 0c
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Creará un nuevo contrato de socios comerciales para el proceso de interfaz de socio (PIP) 0C4.  
  
### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  
  
-   Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for RosettaNet**y, a continuación, haga clic en  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Consola de administración.  
  
### <a name="to-create-the-0c4-trading-partner-agreement"></a>Para crear el contrato de socios comerciales 0C4  
  
1.  En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo** .  
  
2.  En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escriba **Fabrikam_To_Contoso_0C4**.|  
    |**Configuración del proceso**|Seleccione **STD_0C4_R01.02** en la lista desplegable.|  
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
  
5.  Haga clic con el botón derecho en el acuerdo **Fabrikam_To_Contoso_0C4** y, a continuación, haga clic en **Activar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 5: Crear el acuerdo de socio comercial Fabrikam 3A2](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-fabrikam-3a2-trading-partner-agreement.md)