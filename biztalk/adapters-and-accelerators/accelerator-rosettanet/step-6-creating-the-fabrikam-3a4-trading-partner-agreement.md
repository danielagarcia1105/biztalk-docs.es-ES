---
title: 'Paso 6: Creación de los intercambios de Fabrikam 3A4 contrato de socios | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a533f00835b8f2200c539baa0e27fbe51ad2c5f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009549"
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a>Paso 6: Creación del acuerdo de socio comercial Fabrikam 3A4
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo entre socios comerciales para el proceso de interfaz de socio (PIP) de 3A4.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.  

### <a name="to-create-the-3a4-trading-partner-agreement"></a>Para crear el acuerdo de socio comercial de 3A4  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .  

2. En el **nuevas propiedades de acuerdo** cuadro de diálogo el **General** ficha, realice lo siguiente:  


   |         Use          |                      Para                       |
   |---------------------------|-------------------------------------------------------|
   |         **Nombre**          |           Tipo **Fabrikam_To_Contoso_3A4**.           |
   | **Configuración del proceso** |  Seleccione **STD_3A4_V02.02** en la lista desplegable.   |
   |    **Mi organización**    |     Seleccione **Fabrikam** en la lista desplegable.      |
   | **Organización del asociado**  |      Seleccione **Contoso** en la lista desplegable.      |
   |     **Versión RNIF**      |     Seleccione **V02.00.01** en la lista desplegable.     |
   |       **Rol principal**       | Seleccione **comprador (iniciador)** en la lista desplegable. |
   |         **Usage**         |       Seleccione **Prueba** en la lista desplegable.        |


3. En el **puertos** ficha, realice lo siguiente:  


   |    Use    |                          Para                           |
   |----------------|---------------------------------------------------------------|
   | **Dirección URL de acción** | Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**. |
   | **URL de la señal** | Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**. |
   |  **Dirección URL de la sincronización**  | Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**. |


4. Haga clic en **Aceptar**.  

5. Haga clic en el **Fabrikam_To_Contoso_3A4** acuerdo y, a continuación, haga clic en **activar**.  

## <a name="see-also"></a>Vea también  
 [Paso 7: Compilación e implementación del ejemplo de SDK de LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)