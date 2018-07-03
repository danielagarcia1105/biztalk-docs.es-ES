---
title: Cómo agregar cuentas a una vista | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- Add-Account command [BAM]
- managing [BAM], adding accounts to views
ms.assetid: 0875796c-82a4-4165-9bed-88e8ba466548
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39d1d6b29c7f0b2b7704d6634b49b93a0aede738
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985445"
---
# <a name="how-to-add-accounts-to-a-view"></a>Cómo agregar cuentas a una vista
Los administradores utilizan el **Agregar cuenta** comando para asociar usuarios a vistas de BAM y proteger las vistas de hojas de cálculo de Excel de BAM de accesos no autorizados. Cuando los usuarios guardan vistas de BAM, estas vistas hacen referencia a una cadena de conexión de SQL oculta en el libro. El libro está protegido, pero debe asegurarse de que el documento también esté protegido.  
  
 Cuando se asocian usuarios a vistas de BAM, se limita el acceso a las vistas sólo a los usuarios o grupos a los que se concede acceso.  
  
> [!IMPORTANT]
>  Si usa agregaciones en tiempo real (ATR), los usuarios agregados con **Agregar cuenta** no se concede automáticamente derechos de inicio de sesión en el equipo que ejecuta SQL Server. Si está utilizando ATR, considere la posibilidad de establecer un grupo de usuarios de Windows que contenga todos los usuarios que necesitan tener acceso a las vistas de las ATR. Conceda a ese grupo derechos explícitos de inicio de sesión en el servidor SQL Server en el que resida la base de datos de importación principal.  
  
 Para obtener información acerca de cómo ver las vistas de BAM, consulte [cómo enumerar vistas de BAM](../core/how-to-list-bam-views.md).  
  
### <a name="to-add-an-account-to-a-view"></a>Para agregar una cuenta a una vista  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Escriba [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking en el símbolo del sistema para desplazarse hasta la carpeta de seguimiento. Presione **ENTRAR**.  
  
3. Tipo **bm agregar-account - AccountName:\<nombreCuenta\> -View:\<nombre de la vista\>**.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)