---
title: "Descripción de SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- Windows Integrated Single Sign-On
- Extranet Single Sign-On (Web SSO)
- Server-Based Intranet Single Sign-On
ms.assetid: 03f78a7b-4880-408f-9733-d07e19775d21
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736fee720f2abf0dd051b1f754dd0fd6b8c42ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-sso"></a>Entendiendo SSO
Para entender Enterprise Single Sign-On, es útil buscar en los tres tipos de Single Sign-On servicios disponibles hoy en día: integrado de Windows, extranet y de intranet. Estos tipos se describen a continuación, el tercero de los cuales incluye el inicio de sesión único (SSO) empresarial.  
  
## <a name="windows-integrated-single-sign-on"></a>Inicio de sesión único (SSO) integrado de Windows  
 Estos servicios permiten conectarse a varias aplicaciones de la red que utilizan un mecanismo de autenticación común. Estos servicios solicitan y comprueban las credenciales tras iniciar sesión en la red, y utilizan esas credenciales para determinar las acciones que se pueden llevar a cabo en función de los derechos del usuario. Por ejemplo, si las aplicaciones efectúan la integración utilizando Kerberos, se podrá tener acceso a cualquier recurso de la red integrado con Kerberos después de que el sistema lleve a cabo la autenticación de las credenciales.  
  
## <a name="extranet-single-sign-on-web-sso"></a>Inicio de sesión único (SSO web) de extranet  
 Estos servicios permiten el acceso a los recursos a través de Internet utilizando un solo conjunto de credenciales de usuario. El usuario proporciona un conjunto de credenciales para iniciar sesión en diferentes sitios web pertenecientes a distintas organizaciones. Un ejemplo de este tipo de inicio de sesión único (SSO) es Windows Live ID para aplicaciones basadas en consumidores. Para escenarios federados, los Servicios de federación de Active Directory habilitan SSO web.  
  
## <a name="server-based-intranet-single-sign-on"></a>Inicio de sesión único (SSO) de intranet basado en servidor  
 Estos servicios le permiten integrar varios sistemas y aplicaciones heterogéneos en el entorno empresarial. Es posible que estos sistemas y aplicaciones no utilicen una autenticación común. Cada aplicación tiene su propio almacén de directorios de usuario. Por ejemplo, en una organización, Windows utiliza el servicio de directorio Active Directory para autenticar usuarios, y los grandes sistemas (mainframes) utilizan Resource Access Control Facility (RACF) de IBM para autenticar los mismos usuarios. En la empresa, las aplicaciones de software intermedio integran las aplicaciones de servidor y aplicaciones para usuarios. El inicio de sesión único (SSO) empresarial permite a los usuarios de la empresa conectarse tanto a las aplicaciones de servidor como a las aplicaciones para usuarios al utilizar únicamente un conjunto de credenciales. Permite que tanto el inicio de sesión único (SSO) iniciado por Windows (en el que la solicitud inicial se efectúa desde el entorno de dominio de Windows) como el inicio de sesión único (SSO) iniciado por host (en el que la solicitud inicial se efectúa desde un entorno de dominio ajeno a Windows) tengan acceso a un recurso del dominio de Windows.  
  
 Además, **Password Synchronization** simplifica la administración de la base de datos SSO y sincroniza las contraseñas sincronizadas entre directorios de usuario. Esto se lleva a cabo utilizando adaptadores de sincronización de contraseñas, que se pueden configurar y administrar mediante las herramientas de sincronización de contraseñas.  
  
## <a name="the-enterprise-single-sign-on-system"></a>Sistema de inicio de sesión único (SSO) empresarial  
 El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales y de red, incluidos los límites de dominio. SSO almacena las credenciales en la base de datos de SSO. Puesto que SSO proporciona una solución de inicio de sesión único (SSO) genérica, las aplicaciones de software intermedio y los adaptadores personalizados pueden aprovechar SSO para almacenar las credenciales de usuario y transmitirlas por el entorno de forma segura. Los usuarios finales no necesitan recordar distintas credenciales para aplicaciones diferentes.  
  
 El sistema de inicio de sesión (SSO) se compone de una base de datos de SSO, un servidor secreto principal y uno o varios servidores de inicio de sesión único (SSO).  
  
 El sistema SSO contiene aplicaciones afiliadas que el administrador define. Una aplicación afiliada es una entidad lógica que representa un sistema o subsistema, como un host, un sistema de servidor o una aplicación de línea empresarial, al que se conecta mediante el inicio de sesión único (SSO) empresarial. Cada aplicación afiliada tiene varias asignaciones de usuario; por ejemplo, tiene asignaciones establecidas entre las credenciales de un usuario en Active Directory y las credenciales de RACF correspondientes.  
  
 La base de datos de SSO es la base de datos de SQL Server que almacena la información acerca de las aplicaciones afiliadas, así como de todas las credenciales de usuario cifradas de todas las aplicaciones afiliadas.  
  
 El servidor secreto principal es el servidor de inicio de sesión único (SSO) empresarial que almacena el secreto principal. Todos los servidores de inicio de sesión único (SSO) del sistema obtienen el secreto principal del servidor secreto principal.  
  
 El sistema SSO también contiene uno o más servidores de SSO. Estos servidores llevan a cabo la asignación entre las credenciales de servidor y las de Windows, buscan las credenciales en la base de datos de SSO; y los administradores los utilizan para mantener el sistema SSO.  
  
> [!NOTE]
>  Sólo puede tener un servidor secreto principal y una base de datos de SSO en el sistema SSO. La base de datos de SSO puede ser remota con respecto al servidor secreto principal.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Grupos de usuarios SSO](../core/sso-user-groups.md)  
  
-   [Componentes de SSO](../core/sso-components.md)  
  
-   [Servidor de SSO](../core/sso-server.md)  
  
-   [Servidor secreto principal](../core/master-secret-server.md)  
  
-   [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)  
  
-   [Asignaciones de SSO](../core/sso-mappings.md)  
  
-   [Vales de SSO](../core/sso-tickets.md)  
  
-   [Configuración de SSO](../core/configuring-sso.md)