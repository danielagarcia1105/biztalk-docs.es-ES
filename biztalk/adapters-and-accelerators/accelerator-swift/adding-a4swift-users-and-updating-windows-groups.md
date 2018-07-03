---
title: Agregar usuarios de A4SWIFT y actualizar grupos de Windows | Microsoft Docs
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
ms.openlocfilehash: bb276c069a86d060c319f960e666210691b69056
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973333"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a>Agregar usuarios de A4SWIFT y actualizar grupos de Windows
Después de crear e instalar certificados para las funciones de reparación de mensajes y nuevo envío, debe crear [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] a los usuarios y agregar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] a los usuarios a grupos.  
  
 **Resumen**  
  
 Crear usuarios de reparación de mensajes y nuevo envío y agregue las cuentas locales o de dominio al [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] grupos de usuarios, como se indica a continuación:  
  
- En el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración, deberá crear tantos usuarios como funciones en las fases de flujo de trabajo del proceso de reparación de mensajes y nuevo envío. Asociar un certificado diferente a cada uno de estos usuarios.  
  
- Mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos, agregar cada usuario local que está creando, reparación, comprobar o aprobación de un mensaje a los usuarios de A4SWIFT.  
  
- Mediante el [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] utilidad de administración de equipos, agregue el usuario local que se muestra en el campo iniciar sesión como para que el servicio del servicio de BizTalk grupo la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios.  
  
  > [!NOTE]
  >  Para obtener más información acerca de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] usuarios y roles, consulte [creando los departamentos de TI y los Roles de reparación de mensajes y nuevo envío](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a>Para agregar cuentas de usuario al grupo de usuarios de A4SWIFT  
  
1.  Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
2.  En el **administración de equipos** cuadro de diálogo, en el panel izquierdo, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**.  
  
3.  En el **administración de equipos** cuadro de diálogo, en el panel derecho, haga doble clic en **los usuarios de A4SWIFT**.  
  
4.  En el **las propiedades de los usuarios de A4SWIFT** cuadro de diálogo, haga clic en **agregar**.  
  
5.  En el **Seleccionar usuarios, equipos o grupos** cuadro de diálogo el **escriba los nombres de objeto para seleccionar** panel, escriba el nombre de un usuario local que está creando, reparación, comprobar o aprobación de un mensaje y, a continuación, Haga clic en **Aceptar**.  
  
6.  Repita el paso 5 para cada usuario local que está creando, reparación, comprobar o aprobación de un mensaje.  
  
7.  En el cuadro de diálogo Propiedades de los usuarios de A4SWIFT, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Administración de equipos, en el panel izquierdo, expanda Servicios y aplicaciones y, a continuación, haga clic en servicios. En el panel derecho, haga clic en **servicio de BizTalk grupo**. Tenga en cuenta el usuario mencionado en la columna iniciar sesión como para **servicio de BizTalk grupo**.  
  
9. En el panel izquierdo de la **administración de equipos** cuadro de diálogo, expanda **usuarios y grupos locales**y, a continuación, haga clic en **grupos**. Haga doble clic en **los usuarios de A4SWIFT**. Asegúrese de que el usuario aparece en la columna iniciar sesión como para **servicio de BizTalk grupo** forma parte de la **los usuarios de A4SWIFT** grupo. Si no, agregue ese usuario a la **los usuarios de A4SWIFT** grupo.  
  
10. Cierre sesión en el servidor y, a continuación, vuelva a iniciar sesión.