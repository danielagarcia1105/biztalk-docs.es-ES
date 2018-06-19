---
title: Agregar usuarios de A4SWIFT y actualizar grupos de Windows | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, Windows groups
- Windows groups, user accounts
- user accounts, creating
- Windows groups, updating
- updating Windows groups
- A4SWIFT, creating user accounts
ms.assetid: ddc54457-6499-402c-9cc2-f7b17bbc255f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fbf2f3b78b13205b43989c2b0c03909dec392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209932"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a>Agregar usuarios de A4SWIFT y actualizar grupos de Windows
Después de crear e instalar certificados para los roles de reparación de mensajes y nuevo envío, debe crear [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los usuarios y agregue [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] a los usuarios a grupos.  
  
 **Resumen**  
  
 Crear usuarios de reparación de mensajes y nuevo envío y agregar cuentas de dominio o local a [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] grupos de usuarios, como se indica a continuación:  
  
-   En el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración, debe crear tantos usuarios como funciones en las fases de flujo de trabajo del proceso de reparación de mensajes y nuevo envío. Asociar un certificado diferente a cada uno de estos usuarios.  
  
-   Mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos, agregue cada usuario local que está creando, reparación, comprobar o la aprobación de un mensaje a los usuarios de A4SWIFT.  
  
-   Mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos, agregue el usuario local que se muestra en el campo de inicio de sesión para que el servicio del servicio de BizTalk grupo la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios.  
  
    > [!NOTE]
    >  Para obtener más información acerca de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuarios y roles, consulte [crear departamentos y Roles para la reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a>Para agregar cuentas de usuario al grupo de usuarios de A4SWIFT  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  En el **administración de equipos** cuadro de diálogo, en el panel izquierdo, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**.  
  
3.  En el **administración de equipos** cuadro de diálogo, en el panel derecho, haga doble clic en **A4SWIFT usuarios**.  
  
4.  En el **propiedades de los usuarios de A4SWIFT** cuadro de diálogo, haga clic en **agregar**.  
  
5.  En el **Seleccionar usuarios, equipos o grupos** cuadro de diálogo, en la **escriba los nombres de objeto para seleccionar** panel, escriba el nombre de un usuario local que está creando, reparación, comprobar o aprobar un mensaje y, a continuación, Haga clic en **Aceptar**.  
  
6.  Repita el paso 5 para cada usuario local que está creando, reparación, comprobar o aprobar un mensaje.  
  
7.  En el cuadro de diálogo Propiedades de los usuarios de A4SWIFT, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Administración de equipos, en el panel izquierdo, expanda Servicios y aplicaciones y, a continuación, haga clic en servicios. En el panel derecho, haga clic en **servicio de BizTalk grupo**. Tenga en cuenta el usuario mencionado en la columna de inicio de sesión de **servicio de BizTalk grupo**.  
  
9. En el panel izquierdo de la **administración de equipos** cuadro de diálogo, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**. Haga doble clic en **A4SWIFT usuarios**. Asegúrese de que el usuario aparece en la columna de inicio de sesión de **servicio de BizTalk grupo** forma parte de la **A4SWIFT usuarios** grupo. Si no es así, agregue ese usuario a la **A4SWIFT usuarios** grupo.  
  
10. Cerrar la sesión del servidor y, a continuación, volver a iniciar sesión.