---
title: 'Paso 6: Crear los intercambios de Contoso 3A4 contrato de socios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: a20e40d8-7e3b-4930-8921-056ffddd08ea
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531a4b4a5446b51e01800caf582e40ce13bc288f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965018"
---
# <a name="step-6-creating-the-contoso-3a4-trading-partner-agreement"></a>Paso 6: Crear el acuerdo de socio comercial Contoso 3A4
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo de socio comercial para el proceso de interfaz de socio (PIP) 3A4.  
  
### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  
  
-   Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Consola de administración.  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a>Para crear el acuerdo de socio comercial de 3A4  
  
1.  En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo** .  
  
2.  En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Fabrikam_To_Contoso_3A4**.|  
    |**Configuración del proceso**|Seleccione **STD_3A4_V02.02** en la lista desplegable.|  
    |**Mi organización**|Seleccione **Contoso** en la lista desplegable.|  
    |**Organización de socios comerciales**|Seleccione **Fabrikam** en la lista desplegable.|  
    |**Versión RNIF**|Seleccione **V02.00.01** en la lista desplegable.|  
    |**Rol principal**|Seleccione **vendedor (respondedor)** en la lista desplegable.|  
    |**Uso**|Seleccione **prueba** desde la lista desplegable.|  
  
3.  En el **puertos** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de acción**|Tipo de **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**Dirección URL de señal**|Tipo de **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**Dirección URL de la sincronización**|Tipo de **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
  
4.  Haga clic en **Aceptar**.  
  
5.  Haga clic en el **Fabrikam_To_Contoso_3A4** acuerdo y, a continuación, haga clic en **activar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 7: Compilación e implementación del ejemplo de SDK de DoubleAction](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-doubleaction-sdk-sample.md)