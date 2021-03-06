---
title: 'Paso 2: Creación de la organización de socio comercial Fabrikam | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5634b1394a7c390dfddbcf3b893e2496e20a08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004365"
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a>Paso 2: Creación de la organización de socio comercial Fabrikam
En este paso, usará el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración para crear un nuevo socio comercial. El socio comercial para este tutorial es la organización de Fabrikam.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- En el equipo de Contoso, haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** consola de administración.  

### <a name="to-create-fabrikam-as-a-trading-partner"></a>Para crear a Fabrikam socio comercial  

1. En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **asociados**, apunte a **New**y, a continuación, haga clic en **asociado**.  

2. En el cuadro de diálogo Propiedades de nuevo socio, en el **General** ficha, realice lo siguiente<strong>:</strong>  


   |          Use          |                                                                              Para                                                                               |
   |----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |          **Nombre**          |                                                                          Escriba **FABRIKAM**.                                                                           |
   |          **GBI**           | Escriba **987654321**. **Nota:** si ha ejecutado el tutorial de bucle invertido en el mismo equipo, tendrá que especificar un valor para GBI que es diferente de "987654321". |
   | **Clasificación de socio** |                                                              En la lista desplegable, seleccione **Comprador** .                                                              |
   | **Certificado de firma**  |                                                  Seleccione **Fabrikam firma [huella digital]** en la lista desplegable.                                                  |
   | **Certificado de cifrado** |                                                 Seleccione **Fabrikam cifrado [huella digital]** en la lista desplegable.                                                  |


3. Haga clic en la ficha **Propiedades del contacto** y, a continuación, haga lo siguiente:  


   |       Use        |                Para                |
   |-----------------------|------------------------------------------|
   |   **Nombre de contacto**    |            Escriba **Jane Doe**.            |
   |  **E-mail Address**   | Tipo <strong>jdoe@fabrikam.com</strong>. |
   | **Número de teléfono**  |          Escriba **555-555-5555**.          |
   |    **Número de fax**     |          Escriba **555-555-5555**.          |
   | **Código de la cadena de suministro** |     Escriba **Componentes electrónicos**.      |


4. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Paso 3: Creación del acuerdo entre socios comerciales Contoso 0C2](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)