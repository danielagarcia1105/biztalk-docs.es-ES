---
title: 'Paso 5: Creación de los intercambios de 3A2 de Contoso contrato de socios | Microsoft Docs'
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
ms.assetid: 5c602c9c-22bd-450f-bb14-6848b1414c03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d4004b7ac0d068a2f2621affc34f18ecf21f9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970629"
---
# <a name="step-5-creating-the-contoso-3a2-trading-partner-agreement"></a>Paso 5: Creación del acuerdo de socios comerciales Contoso 3A2
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo entre socios comerciales para el proceso de interfaz de socio (PIP) de 3A2.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.  

### <a name="to-create-the-3a2-trading-partner-agreement"></a>Para crear el acuerdo de socio comercial de 3A2  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .  

2. En el **nuevas propiedades de acuerdo** cuadro de diálogo el **General** ficha, realice lo siguiente:  


   |         Use          |                            Para                            |
   |---------------------------|------------------------------------------------------------------|
   |         **Nombre**          |                Tipo **Fabrikam_To_Contoso_3A2**.                 |
   | **Configuración del proceso** |      Seleccione **STD_3A2_R02.00.00A** en la lista desplegable.      |
   |    **Mi organización**    |           Seleccione **Contoso** en la lista desplegable.            |
   | **Organización del asociado**  |           Seleccione **Fabrikam** en la lista desplegable.           |
   |     **Versión RNIF**      |          Seleccione **V02.00.01** en la lista desplegable.           |
   |       **Rol principal**       | Seleccione **proveedor del producto (respondedor)** en la lista desplegable. |
   |         **Usage**         |             Seleccione **Prueba** en la lista desplegable.             |


3. Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:  


   |    Use    |                          Para                           |
   |----------------|---------------------------------------------------------------|
   | **Dirección URL de acción** | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   | **URL de la señal** | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   |  **Dirección URL de la sincronización**  | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |


4. Haga clic en **Aceptar**.  

5. Haga clic en el **Fabrikam_To_Contoso_3A2** acuerdo y, a continuación, haga clic en **activar**.  

## <a name="see-also"></a>Vea también  
 [Paso 6: Creación del acuerdo entre socios comerciales Contoso 3A4](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-contoso-3a4-trading-partner-agreement.md)