---
title: 'Paso 1: Creación de la organización principal Contoso | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating home organizations
- creating, home organizations
- home organizations, creating
ms.assetid: 0e7a53b9-ae59-4cd1-88bd-0ada7e65acba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303048a06ce1acccac07d10bbe1ac53c32a08122
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000125"
---
# <a name="step-1-creating-the-contoso-home-organization"></a>Paso 1: Creación de la organización principal Contoso
En este paso, usará el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración para crear la organización principal Contoso.  

### <a name="to-start-the-btarn-management-console"></a>Para iniciar la consola de administración de BTARN  

- En el equipo de Contoso, haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** consola de administración.  

### <a name="to-create-the-home-organization"></a>Para crear la organización principal  

1. En el [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **organizaciones principales**, apunte a **New**y, a continuación, haga clic en **organización principal**.  

2. En el cuadro de diálogo nuevas propiedades de organización de inicio, en el **General** ficha, realice lo siguiente:  


   |               Use               |                                                                              Para                                                                               |
   |--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |               **Nombre**               |                                                                           Escriba **CONTOSO**.                                                                           |
   |               **GBI**                | Escriba **123456789**. **Nota:** si ha ejecutado el tutorial de bucle invertido en el mismo equipo, tendrá que especificar un valor para GBI que es diferente de "123456789". |
   | **Clasificación de la organización principal** |                                                           En la lista desplegable, seleccione **Fabricante** .                                                            |


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
 [Paso 2: Creación de la organización asociada Fabrikam](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)