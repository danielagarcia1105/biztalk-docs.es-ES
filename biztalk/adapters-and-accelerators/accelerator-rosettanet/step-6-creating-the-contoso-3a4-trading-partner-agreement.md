---
title: 'Paso 6: Creación de los intercambios de Contoso 3A4 contrato de socios | Microsoft Docs'
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
ms.openlocfilehash: 4159622ea868e207752e6b8d008746f5400da4fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002869"
---
# <a name="step-6-creating-the-contoso-3a4-trading-partner-agreement"></a>Paso 6: Creación del acuerdo de socios comerciales Contoso 3A4
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo entre socios comerciales para el proceso de interfaz de socio (PIP) de 3A4.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.  

### <a name="to-create-the-3a4-trading-partner-agreement"></a>Para crear el acuerdo de socio comercial de 3A4  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .  

2. En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:  


   |         Use          |                       Para                       |
   |---------------------------|--------------------------------------------------------|
   |         **Nombre**          |           Tipo **Fabrikam_To_Contoso_3A4**.            |
   | **Configuración del proceso** |   Seleccione **STD_3A4_V02.02** en la lista desplegable.   |
   |    **Mi organización**    |      Seleccione **Contoso** en la lista desplegable.       |
   | **Organización del asociado**  |      Seleccione **Fabrikam** en la lista desplegable.      |
   |     **Versión RNIF**      |     Seleccione **V02.00.01** en la lista desplegable.      |
   |       **Rol principal**       | Seleccione **vendedor (respondedor)** en la lista desplegable. |
   |         **Usage**         |        Seleccione **prueba** desde la lista desplegable.        |


3. En el **puertos** ficha, realice lo siguiente:  


   |    Use    |                          Para                           |
   |----------------|---------------------------------------------------------------|
   | **Dirección URL de acción** | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   | **URL de la señal** | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   |  **Dirección URL de la sincronización**  | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |


4. Haga clic en **Aceptar**.  

5. Haga clic en el **Fabrikam_To_Contoso_3A4** acuerdo y, a continuación, haga clic en **activar**.  

## <a name="see-also"></a>Vea también  
 [Paso 7: Compilación e implementación del ejemplo de SDK de DoubleAction](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-doubleaction-sdk-sample.md)