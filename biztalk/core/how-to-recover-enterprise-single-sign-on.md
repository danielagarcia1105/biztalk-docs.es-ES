---
title: Cómo recuperar Enterprise Single Sign-On | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56953fcab29b53f23ba3097296a74aeb67a17c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973125"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a>Cómo recuperar el inicio de sesión único (SSO) empresarial
Antes de poder recuperar BizTalk Server, es preciso recuperar el inicio de sesión único (SSO) empresarial.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Para llevar a cabo esta tarea, debe haber iniciado sesión como miembro del grupo de administradores de inicio de sesión único y del grupo de administradores.  
  
-   Es preciso disponer de la contraseña utilizada durante la configuración de SSO.  
  
-   Todas las bases de datos están intactas en el servidor remoto.  
  
-   El archivo de copia de seguridad del secreto principal está intacto y se encuentra almacenado en un lugar seguro.  
  
### <a name="to-recover-enterprise-single-sign-on"></a>Para recuperar el inicio de sesión único empresarial  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
2. Configuración de Microsoft BizTalk Server, en el árbol de consola, haga clic en **SSO empresarial**.  
  
3. En el panel de detalles, seleccione **habilitar Enterprise Single Sign-On en este equipo**y, a continuación, haga clic en **unir un sistema SSO existente**.  
  
4. En **almacena datos**, escriba el nombre de SQL server que hospeda la base de datos SSO y el nombre de la base de datos SSO.  
  
5. En **servicio Windows**, escriba el nombre de usuario y la contraseña para la cuenta de servicio de inicio de sesión único que usó al instalar y configurar BizTalk Server originalmente.  
  
   > [!NOTE]
   >  Se puede utilizar una cuenta distinta, pero, para ello, es preciso que ésta pertenezca al grupo de administradores de inicio de sesión único.  
  
6. Haga clic en **Aplicar configuración**.  
  
    Aparecerá una advertencia de que no se recuperó ningún secreto principal. Se puede utilizar el Visor de sucesos para comprobar que se ha iniciado el servicio de inicio de sesión único empresarial y que se ejecuta en el equipo.  
  
7. Haga clic en **archivo**y, a continuación, haga clic en **Exit**.  
  
8. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
9. En el símbolo del sistema, escriba:  
  
     **CD programa archivos de programa\Archivos comunes\enterprise Single Sign-On**  
  
10. En el símbolo del sistema, escriba:  
  
     **ssoconfig - restoreSecret***\<backupfile  \>*  
  
     donde *\<backupfile\>* es el nombre del archivo secreto maestro que hizo copia de seguridad.  
  
     Cuando **ssoconfig** le pedirá la contraseña del archivo de copia de seguridad, escriba la contraseña que especificó durante la configuración de SSO. Si la contraseña es correcta, **ssoconfig** muestra el mensaje siguiente:  
  
     **La operación se completó correctamente**  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)   
 [Configurar Enterprise SSO mediante la configuración de BizTalk Server](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)