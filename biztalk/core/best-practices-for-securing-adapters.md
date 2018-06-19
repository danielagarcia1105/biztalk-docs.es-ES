---
title: Prácticas recomendadas para proteger los adaptadores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- best practices, adapters
- adapters, permissions
- security, adapters
- permissions, adapters
- best practices, security
- adapters, best practices
ms.assetid: 004e1a01-b316-4eee-967f-5a806431de2b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86abbba06e851b9b289b29cd7fbbf01b3af292a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233300"
---
# <a name="best-practices-for-securing-adapters"></a>Prácticas recomendadas para proteger los adaptadores
En este tema se ofrece una lista de las prácticas recomendadas para la seguridad de los adaptadores.  
  
 **No instale a los adaptadores que no se confía en el equipo; usar sólo certificados de socios comerciales de desarrollo de adaptador.**  
  
 **No almacene datos confidenciales de clientes en el esquema de adaptador predeterminado.**  
  
 Debería configurar la información de la contraseña y el nombre de usuario una vez implementado un adaptador. Esto garantiza que la información se almacena en la base de datos de SSO. Para obtener más información acerca de la base de datos SSO, vea [mediante SSO](../core/using-sso.md).  
  
 **Conceda los permisos siguientes en las carpetas compartidas (la carpeta de recepción y envío carpeta) que se utilizan para recoger archivos y colocarlos utilizando los adaptadores de EDI y de archivo:**  
  
-   **Carpeta de recepción**  
  
     La carpeta de recepción para el adaptador de archivo puede configurarse en la ubicación de recepción. La carpeta de recepción para el adaptador de EDI puede configurarse en el controlador de recepción. La cuenta de servicio para el host de BizTalk que recoge el archivo debería tener los permisos siguientes en el nivel del sistema de archivos:  
  
    -   Enumerar carpetas o leer datos  
  
    -   Eliminar subcarpetas y archivos  
  
     Si la carpeta de recepción se encuentra en un recurso compartido de red, se deben conceder los siguientes permisos en el nivel de recurso compartido de archivos:  
  
    -   La cuenta de servicio para el host de BizTalk que recoge el archivo debe tener los permisos de control total:  
  
    -   Los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deben contar con permisos de control total para la solución de problemas.  
  
    -   Los programas o usuarios externos que coloquen archivos en esta ubicación deben tener permisos de escritura.  
  
-   **Carpeta de envío**  
  
     La carpeta de envío para los adaptadores de EDI y de archivo puede configurarse en el puerto de envío.  
  
    -   La cuenta de servicio para los hosts o el host de BizTalk que coloca archivos en esta ubicación debe contar con permisos de escritura.  
  
    -   Los administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deben tener permisos de control total.  
  
    -   Los programas o usuarios externos que recojan archivos de esta ubicación deben tener permisos de lectura.  
  
 **Agregue la cuenta de usuario en el que se ejecuta el servicio EDI al rol BTS_HOST_USERS SQL.**  
  
 Esto resulta necesario para que se pueda obtener acceso a la administración de objetos (OM) del Explorador de BizTalk sin contar con permisos administrativos. Para ello, agregue "Usuarios del subsistema EDI" al rol BTS_HOST_USERS en la base de datos de administración de BizTalk, BizTalkMgmtDb.  
  
 Para agregar "Usuarios del subsistema EDI" al rol BTS_HOST_USERS en SQL Server 2005, lleve a cabo los siguientes pasos:  
  
1.  Inicie SQL Server Management Studio desde **inicio, programas, Microsoft SQL Server 2008**.  
  
2.  Efectúe la conexión con el servidor SQL Server que aloja la base de datos de administración de BizTalk.  
  
3.  Expanda este servidor en el Explorador de objetos.  
  
4.  Expanda **bases de datos**y, a continuación, expanda la base de datos de administración de BizTalk.  
  
5.  Expanda **seguridad**, expanda **Roles**y, a continuación, haga clic para seleccionar **Roles de base de datos**  
  
6.  En el panel de detalles, haga clic en el rol BTS_HOST_USERS y, a continuación, haga clic en **propiedades**.  
  
7.  En el cuadro de diálogo BTS_HOST_USERS, haga clic en **agregar**, haga clic en **examinar**y, a continuación, active la casilla situada junto al grupo de usuarios del subsistema EDI para agregarlo.  
  
     Si el grupo Usuarios del subsistema EDI no se encuentra en la lista de usuarios para agregarlo, debe agregar el grupo Usuarios del subsistema EDI como un nuevo usuario de la base de datos a la base de datos de administración. Para agregar el grupo Usuarios del subsistema EDI como un nuevo usuario de la base de datos, lleve a cabo los pasos siguientes en SQL Server Management Studio:  
  
    1.  Expanda la base de datos de administración de BizTalk.  
  
    2.  Expanda **seguridad**.  
  
    3.  Haga clic en **usuarios** y haga clic en **nuevo usuario**.  
  
    4.  Haga clic en el botón de puntos suspensivos (...) situado junto al cuadro de texto para **nombre de inicio de sesión** para mostrar la **seleccionar inicio de sesión** cuadro de diálogo.  
  
    5.  Haga clic en el botón Examinar, escriba la **usuarios del subsistema EDI** de grupo y, a continuación, haga clic en **Aceptar.** Si se le solicita con la **varios objetos encontrados** cuadro de diálogo, seleccione la **usuarios del subsistema EDI** inicio de sesión y haga clic en **Aceptar**.  
  
    6.  En el **usuario de base de datos - nuevo** cuadro de diálogo Escriba **usuarios del subsistema EDI** para el **nombre de usuario** cuadro de texto y haga clic en **Aceptar**.  
  
 **Agregue la cuenta de usuario bajo la que se ejecuta el servicio de BizTalk al grupo de usuarios del subsistema EDI.**  
  
 Siga los pasos que se indican a continuación para agregar la cuenta de usuario para el servicio de BizTalk al grupo Usuarios del subsistema EDI.  
  
-   **Si BizTalk Server está configurado para usar grupos de dominio:**  
  
    1.  Inicie sesión en un equipo con Windows Server del dominio.  
  
    2.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **equipos y usuarios de Active Directory**.  
  
        > [!NOTE]
        >  Debe tener permisos de nivel de dominio adecuado para modificar objetos en el **equipos y usuarios de Active Directory** interfaz.  
  
    3.  Haga clic para expandir el contenedor de dominio y haga clic para expandir el **usuarios** contenedor.  
  
    4.  Haga doble clic en el **usuarios del subsistema EDI** grupo para mostrar las propiedades para este grupo.  
  
    5.  Haga clic en el **miembros** pestaña de la **usuarios del subsistema EDI** cuadro de diálogo grupo.  
  
    6.  Haga clic en el **agregar** botón para agregar la cuenta de usuario para el BizTalk Service a este grupo.  
  
    7.  Haga clic en **Aceptar**.  
  
-   **Si BizTalk Server está configurado para usar grupos locales:**  
  
    1.  Inicie sesión en el servidor BizTalk Server.  
  
    2.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **administración de equipos**.  
  
    3.  Haga clic para expandir **herramientas del sistema**, haga clic para expandir **usuarios y grupos locales**y haga clic para expandir **grupos**.  
  
    4.  Haga doble clic en el **usuarios del subsistema EDI** grupo para mostrar las propiedades para este grupo.  
  
    5.  Haga clic en el **agregar** botón para agregar la cuenta de usuario para el servicio de BizTalk a este grupo.  
  
    6.  Haga clic en **Aceptar**.