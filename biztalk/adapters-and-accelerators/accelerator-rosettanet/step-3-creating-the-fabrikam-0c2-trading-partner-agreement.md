---
title: 'Paso 3: Creación del acuerdo de socios comerciales 2 de Fabrikam 0c | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 4552f712-f226-423f-b06d-98e943e8efd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c10881f1ac703f07d6daaf2a87abd96f3086672b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970269"
---
# <a name="step-3-creating-the-fabrikam-0c2-trading-partner-agreement"></a>Paso 3: Creación del acuerdo de socios comerciales 2 de Fabrikam 0c
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Crear un nuevo acuerdo entre socios comerciales para el 0c 2 proceso de interfaz de socio (PIP).  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.  

### <a name="to-create-the-0c2-trading-partner-agreement"></a>Para crear el 0c contrato de socios comerciales de 2  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .  

2. En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:  


   |         Use          |                        Para                         |
   |---------------------------|-----------------------------------------------------------|
   |         **Nombre**          |             Tipo **Fabrikam_To_Contoso_0C2**.             |
   | **Configuración del proceso** |    Seleccione **STD_0C2_R01.02** en la lista desplegable.     |
   |    **Mi organización**    |       Seleccione **Fabrikam** en la lista desplegable.        |
   | **Organización del asociado**  |        Seleccione **Contoso** en la lista desplegable.        |
   |     **Versión RNIF**      |       Seleccione **V02.00.01** en la lista desplegable.       |
   |       **Rol principal**       | Seleccione **iniciador (iniciador)** en la lista desplegable. |
   |         **Usage**         |         Seleccione **Prueba** en la lista desplegable.          |


3. Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:  


   |    Use    |                          Para                           |
   |----------------|---------------------------------------------------------------|
   | **Dirección URL de acción** | Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**. |
   | **URL de la señal** | Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**. |
   |  **Dirección URL de la sincronización**  | Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**. |


4. Haga clic en **Aceptar**.  

5. Haga clic en el **Fabrikam_To_Contoso_0C2** acuerdo y, a continuación, haga clic en **activar**.  

## <a name="see-also"></a>Vea también  
 [Paso 4: Creación del acuerdo entre socios comerciales Fabrikam 0C4](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)