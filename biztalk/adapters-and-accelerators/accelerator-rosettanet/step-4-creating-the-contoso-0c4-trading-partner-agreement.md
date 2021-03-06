---
title: 'Paso 4: Creación del acuerdo de socios comerciales 4 de Contoso 0c | Microsoft Docs'
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
ms.assetid: de2a943f-945a-4bfc-87f3-dd327d5214ef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90344af2c2aa1198ecdf95a69a5e411d6097cbc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002093"
---
# <a name="step-4-creating-the-contoso-0c4-trading-partner-agreement"></a>Paso 4: Creación del acuerdo de socios comerciales 4 de Contoso 0c
En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración. Creará un nuevo contrato de socios comerciales para el proceso de interfaz de socio (PIP) 0C4.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Consola de administración.  

### <a name="to-create-the-0c4-trading-partner-agreement"></a>Para crear el contrato de socios comerciales 0C4  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .  

2. En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:  


   |         Use          |                        Para                         |
   |---------------------------|-----------------------------------------------------------|
   |         **Nombre**          |             Escriba **Fabrikam_To_Contoso_0C4**.             |
   | **Configuración del proceso** |    Seleccione **STD_0C4_R01.02** en la lista desplegable.     |
   |    **Mi organización**    |        Seleccione **Contoso** en la lista desplegable.        |
   | **Organización del asociado**  |       Seleccione **Fabrikam** en la lista desplegable.        |
   |     **Versión RNIF**      |       Seleccione **V02.00.01** en la lista desplegable.       |
   |       **Rol principal**       | Seleccione **Respondedor (Respondedor)** en la lista desplegable. |
   |         **Usage**         |         Seleccione **Prueba** en la lista desplegable.          |


3. Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:  


   |    Use    |                          Para                           |
   |----------------|---------------------------------------------------------------|
   | **Dirección URL de acción** | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   | **URL de la señal** | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   |  **Dirección URL de la sincronización**  | Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |


4. Haga clic en **Aceptar**.  

5. Haga clic con el botón derecho en el acuerdo **Fabrikam_To_Contoso_0C4** y, a continuación, haga clic en **Activar**.  

## <a name="see-also"></a>Vea también  
 [Paso 5: Creación del acuerdo entre socios comerciales Contoso 3A2](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-contoso-3a2-trading-partner-agreement.md)