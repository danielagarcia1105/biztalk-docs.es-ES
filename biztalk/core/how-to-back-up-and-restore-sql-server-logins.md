---
title: "Cómo realizar copias de y restaurar inicios de sesión SQL Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54fa6a51a27f82add8a96c613e36f5ed7ce88e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a>Cómo realizar copias de seguridad y restaurar inicios de sesión de SQL Server
Copia de seguridad y restaurar inicios de sesión de SQL Server asociados con BizTalk Server.  
  
## <a name="biztalk-server-sql-server-security-logins"></a>Inicios de sesión de seguridad de SQL Server de BizTalk Server  
 Los siguientes inicios de sesión de seguridad de SQL Server están asociados con BizTalk Server. Es posible que tenga inicios de sesión adicionales asociados con las aplicaciones de BizTalk Server que haya creado. Debe realizar una copia de seguridad de los inicios de sesión y restaurarlos al mover las bases de datos de BizTalk Server a un nuevo servidor o una nueva instancia de SQL Server.  
  
-   Usuarios de aplicación de BizTalk  
  
-   Usuarios de hosts aislados de BizTalk  
  
-   Administradores de servidor BizTalk Server  
  
-   Operadores de servidor BizTalk Server  
  
-   Administradores de SSO  

## <a name="prerequisites"></a>Requisitos previos  
Debe ser un miembro de la **administradores** rol de seguridad en el servidor SQL Server donde una copia de seguridad y restaurar los inicios de sesión.  
  
## <a name="back-up-a-login-using-a-script"></a>Copia de seguridad de un inicio de sesión mediante un script  
  
1.  Abra **SQL Server Management Studio**.  
  
2.  Expanda **seguridad**y expanda la lista de **inicios de sesión**.  
  
3.  Haga clic en el inicio de sesión que desea crear un script para copia de seguridad y, a continuación, seleccione **secuencia de comandos de inicio de sesión como**.  
  
4.  Seleccione **CREATE To**y, a continuación, seleccione uno de **nueva ventana del Editor de consultas**, **archivo**, o **Portapapeles** para seleccionar un destino para la secuencia de comandos. Normalmente, el destino es un archivo con un **.sql** extensión.  
  
5.  Repita este procedimiento en el paso 3 para cada inicio de sesión que desee incluir en el script. Consulte la lista de inicios de sesión relacionados con BizTalk Server para determinar qué inicios de sesión debe incluir en el script.  
  
## <a name="restore-a-login-from-a-script"></a>Restaurar un inicio de sesión desde un script  
  
1.  Abra **SQL Server Management Studio**.  
  
2.  En el **archivo** menú, **abiertos** el archivo que contiene el inicio de sesión con scripts.  
  
3.  Ejecute el script para crear el inicio de sesión.