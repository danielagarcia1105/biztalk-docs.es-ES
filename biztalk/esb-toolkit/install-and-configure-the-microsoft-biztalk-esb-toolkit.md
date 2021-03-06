---
title: Instalar y configurar Microsoft BizTalk ESB Toolkit | Microsoft Docs
description: Instrucciones paso a paso para instalar y configurar el Kit de herramientas de ESB en BizTalk Server
caps.latest.revision: 8
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 7018a6bfa9d55b58cadfa9b808d7c295f88a2c0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981381"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a>Instalar y configurar el Kit de herramientas de Microsoft BizTalk ESB
A partir de BizTalk Server 2013 y versiones posteriores, [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se integra con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] el programa de instalación. Este tema muestra cómo instalar y configurar [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]y también incluye un vínculo escrito por la Comunidad para actualizar el Kit de herramientas ESB.  
  
> [!IMPORTANT]
>  Debe tener BizTalk Server instalado antes de iniciar la instalación de [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].  
  
## <a name="install"></a>Install 
  
1. Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] archivo setup.exe como administrador. En el programa de instalación, seleccione **instalar [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** .  
  
2. Acepte el contrato de licencia y, a continuación, seleccione **siguiente**.  
  
3. En **Instalación de componentes**, elija los componentes que quiere instalar y seleccione **Siguiente**.  
  
4. En el **resumen**, revise lo que ha elegido y, a continuación, seleccione **instalar**.  
  
5. Seleccione **Finalizar** para cerrar el Asistente para instalación.  

Se crea un archivo de registro de instalación, similar a 'C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm'. 
  
## <a name="configure"></a>Configurar 
  
> [!IMPORTANT]
>  Debe configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] antes de configurar [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].  
  
1. Desde el **iniciar** menú, seleccione **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** y, a continuación, seleccione **herramienta de configuración de ESB**.  
  
   > [!IMPORTANT]
   >  Ejecute la herramienta de configuración de ESB como administrador.  
  
2. En la configuración, seleccione **el servidor de base de datos**. Escriba el nombre del servidor de base de datos que hospeda el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] bases de datos.   
  
3. En **servicios Web de IIS**, escriba la cuenta de usuario y la contraseña que se ejecuta a las aplicaciones de IIS creadas por el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]. A continuación, especifique el sitio Web de IIS que hospeda las aplicaciones.  
  
4. El **grupos de usuarios de BizTalk** enumera los grupos de usuarios de forma predeterminada se utiliza normalmente para la configuración de ESB.  
  
   > [!IMPORTANT]
   >  En esta fase, puede seleccionar **aplicar configuración** para configurar el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] con estos valores predeterminados. Sin embargo, si desea realizar una configuración personalizada, complete los pasos restantes. Los valores de RHE que especifique en los pasos siguientes tienen prioridad sobre los valores predeterminados.  
  
5. En el panel izquierdo, expanda **configuración de ESB**, expanda ** excepción administración ** y, a continuación:  
  
   -   Si no desea configurar una base de datos de administración de excepciones, a continuación, seleccione **base de datos**y desactive el **habilitar base de datos de administración de excepciones**.
  
   -   Si desea usar una base de datos existente en lugar de crear una nueva base de datos, a continuación, seleccione **base de datos**y seleccione el **usar base de datos existente**. Escriba el nombre del servidor de base de datos y el nombre de la base de datos.  
  
   -   Si no desea configurar el servicio web de excepción, a continuación, seleccione **servicios Web de excepciones**y desactive la opción **habilitar servicios de excepciones**.  Si desea ejecutar estos servicios en otro sitio Web, puede escribir aquí.  
  
6. En el panel izquierdo, expanda **componentes principales de ESB**y, a continuación:  
  
   -   Si no desea configurar una base de datos de itinerario, a continuación, seleccione **Itinerary Database**y desactive la opción **Itinerary Database** .  
  
   -   Si desea usar una base de datos de itinerario existente, a continuación, seleccione **Itinerary Database**y seleccione **usar base de datos existente**. Escriba el nombre del servidor de base de datos y el nombre de la base de datos.  
  
   -   Si no desea configurar estos servicios web, a continuación, seleccione **servicios Web principales**y desactive la opción **habilitar servicios principales**. Si desea ejecutar estos servicios en otro sitio Web, puede escribir aquí.
  
7. En el panel izquierdo, seleccione **configuración**.  
   Si está instalando y configurando el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] en un entorno de servidor único, seleccione **origen de archivo de configuración**. Si está configurando una implementación en varias máquinas, seleccione el **origen de configuración de SSO**y, a continuación, escriba lo siguiente:  
  
   -   **Servidor de SSO**: escriba el nombre del servidor SSO
  
   -   **Archivo de configuración**: seleccione los puntos suspensivos **(...)** y, a continuación, busque el archivo esb.config (\Program Files (x86) \Microsoft BizTalk ESB Toolkit)
  
   -   **Nombre de la aplicación**: escriba un nombre para la aplicación de inicio de sesión único. Por ejemplo, escriba `ESB Toolkit`.  
  
   -   **Información de contacto**: escriba una dirección de correo electrónico válida la información de contacto correspondiente en el siguiente formato: `someone@example.com`.  
  
   -   **Nombre del grupo de administradores**: seleccione los puntos suspensivos **(...)** y, a continuación, busque el grupo de administración adecuado  
  
   -   **Nombre del grupo de usuarios**: seleccione los puntos suspensivos **(...)** y, a continuación, vaya al grupo adecuado  

8. Seleccione **aplicar configuración**. Abra IIS y observe que las aplicaciones necesarias para [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] se han creado en el sitio web que ha especificado al configurar [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].  
  
9. En el **herramienta de configuración de ESB**, seleccione **aplicaciones de BizTalk ESB**y, a continuación:  
  
   - Seleccione **habilitar componentes principales de ESB en BizTalk Server** para crear la aplicación en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Seleccione **usar enlace predeterminado** para enlazar esta aplicación al host predeterminado. Seleccione **no usar enlace predeterminado** si no desea enlazar la aplicación al host predeterminado. En este escenario, debe enlazar explícitamente la aplicación en un host una vez creada la aplicación.  
  
   - Seleccione **habilitar componentes JMS/WMQ de ESB en BizTalk Server** para crear la aplicación en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Seleccione **usar enlace predeterminado** para enlazar esta aplicación al host predeterminado. Seleccione **no usar enlace predeterminado** si no desea enlazar la aplicación al host predeterminado. En este escenario, debe enlazar explícitamente la aplicación en un host una vez creada la aplicación.  
  
   - Seleccione **aplicar configuración** para crear las aplicaciones que ha seleccionado. Asegúrese de que las aplicaciones se han creado en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="upgrade-esb-toolkit--community-addition"></a>Actualizar el Kit de herramientas ESB: adición de la Comunidad  
 [Actualización de ESB Toolkit 2.1 a 2.2 local](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)

## <a name="see-also"></a>Vea también
[Solucionar problemas de errores & resoluciones de problemas de instalación y comunes](troubleshooting-the-biztalk-esb-toolkit.md)