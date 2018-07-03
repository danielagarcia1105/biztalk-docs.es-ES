---
title: 'Paso 2: Creación de la organización del asociado de Contoso | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating partner organizations
ms.assetid: ebb3b166-3781-40b9-89d4-2ca0c83d05f3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97e811493c1347bc016671469da8a0dc18483e85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969781"
---
# <a name="step-2-creating-the-contoso-partner-organization"></a>Paso 2: Creación de la organización del asociado de Contoso
En este paso, usará el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración para crear un nuevo socio comercial. El socio comercial para este tutorial es la organización de Contoso.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.  

### <a name="to-create-fabrikam-as-a-trading-partner"></a>Para crear a Fabrikam socio comercial  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **asociados**, apunte a **New**y, a continuación, haga clic en **asociado**.  

2. En el cuadro de diálogo Propiedades de nuevo socio, en el **General** ficha, realice lo siguiente<strong>:</strong>  


   |          Use          |                             Para                              |
   |----------------------------|---------------------------------------------------------------------|
   |          **Nombre**          |                          Escriba **CONTOSO**.                          |
   |          **GBI**           |                         Escriba **123456789**.                         |
   | **Clasificación de socio** |          En la lista desplegable, seleccione **Fabricante** .           |
   | **Certificado de firma**  | Seleccione **Firma de Contoso [huella digital]** en la lista desplegable.  |
   | **Certificado de cifrado** | Seleccione **Cifrado de Contoso [huella digital]** en la lista desplegable. |


3. Haga clic en la ficha **Propiedades del contacto** y, a continuación, haga lo siguiente:  


   |       Use        |               Para                |
   |-----------------------|-----------------------------------------|
   |   **Nombre de contacto**    |           Escriba **John Doe**.            |
   |  **E-mail Address**   | Tipo <strong>jdoe@contoso.com</strong>. |
   | **Número de teléfono**  |         Escriba **555-555-5555**.          |
   |    **Número de fax**     |         Escriba **555-555-5555**.          |
   | **Código de la cadena de suministro** |     Escriba **Componentes electrónicos**.     |


4. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Paso 3: Creación del acuerdo entre socios comerciales Fabrikam 0C2](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)