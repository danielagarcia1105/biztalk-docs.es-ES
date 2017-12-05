---
title: "Cómo recuperar el inicio de sesión único empresarial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a87404e608789fa3dba003f3aba6155c5f049e8d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-recover-enterprise-single-sign-on"></a>Cómo recuperar el inicio de sesión único (SSO) empresarial
Antes de poder recuperar BizTalk Server, es preciso recuperar el inicio de sesión único (SSO) empresarial.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Para llevar a cabo esta tarea, debe haber iniciado sesión como miembro del grupo de administradores de inicio de sesión único y del grupo de administradores.  
  
-   Es preciso disponer de la contraseña utilizada durante la configuración de SSO.  
  
-   Todas las bases de datos están intactas en el servidor remoto.  
  
-   El archivo de copia de seguridad del secreto principal está intacto y se encuentra almacenado en un lugar seguro.  
  
### <a name="to-recover-enterprise-single-sign-on"></a>Para recuperar el inicio de sesión único empresarial  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
2.  Configuración de Microsoft BizTalk Server, en el árbol de consola, haga clic en **SSO empresarial**.  
  
3.  En el panel de detalles, seleccione **habilitar Enterprise Single Sign-On en este equipo**y, a continuación, haga clic en **unir un sistema SSO existente**.  
  
4.  En **almacenes de datos**, escriba el nombre de SQL server que hospeda la base de datos SSO y el nombre de la base de datos SSO.  
  
5.  En **servicio de Windows**, escriba el nombre de usuario y la contraseña para la cuenta de servicio SSO que usó al instalar y configurar BizTalk Server originalmente.  
  
    > [!NOTE]
    >  Se puede utilizar una cuenta distinta, pero, para ello, es preciso que ésta pertenezca al grupo de administradores de inicio de sesión único.  
  
6.  Haga clic en **Aplicar configuración**.  
  
     Aparecerá una advertencia de que no se recuperó ningún secreto principal. Se puede utilizar el Visor de sucesos para comprobar que se ha iniciado el servicio de inicio de sesión único empresarial y que se ejecuta en el equipo.  
  
7.  Haga clic en **archivo**y, a continuación, haga clic en **Exit**.  
  
8.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
9. En el símbolo del sistema, escriba:  
  
     **CD programa programa\Archivos comunes\enterprise Single Sign-On**  
  
10. En el símbolo del sistema, escriba:  
  
     **ssoconfig - restoreSecret***\<backupfile  \>*  
  
     donde  *\<backupfile\>*  es el nombre del archivo secreto maestro que hizo copia de seguridad.  
  
     Cuando **ssoconfig** le pide la contraseña del archivo de copia de seguridad, escriba la contraseña que se especificó durante la configuración de SSO. Si la contraseña es correcta, **ssoconfig** muestra el siguiente mensaje:  
  
     **La operación se completó correctamente**  
  
## <a name="see-also"></a>Vea también  
 [Recuperar un equipo que ejecuta BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md)   
 [Configuración de Enterprise SSO mediante la configuración de BizTalk Server](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)