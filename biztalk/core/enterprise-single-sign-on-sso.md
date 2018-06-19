---
title: Enterprise Single Sign-On (SSO) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6cbc5f514d13cd8457cd9417be5ea5b78408e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240156"
---
# <a name="enterprise-single-sign-on-sso"></a>Inicio de sesión único (SSO) empresarial.
El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales y de red, incluidos los límites de dominio. SSO almacena las credenciales en la base de datos de SSO. Puesto que SSO proporciona una solución de inicio de sesión único (SSO) genérica, las aplicaciones de software intermedio y los adaptadores personalizados pueden aprovechar SSO para almacenar las credenciales de usuario y transmitirlas por el entorno de forma segura. Los usuarios finales no necesitan recordar distintas credenciales para aplicaciones diferentes.  
  
 El sistema de inicio de sesión (SSO) se compone de una base de datos de SSO, un servidor secreto principal y uno o varios servidores de inicio de sesión único (SSO).  
  
 Contiene el sistema SSO *aplicaciones afiliadas* que define un administrador. Un *aplicación afiliada* es una entidad lógica que representa un sistema o subsistema, como un host, el sistema back-end o la línea de aplicaciones empresariales para que se conecta mediante Enterprise Single Sign-On. Cada aplicación afiliada tiene varias asignaciones de usuario; por ejemplo, tiene asignaciones establecidas entre las credenciales de un usuario en Active Directory y las credenciales de RACF correspondientes.  
  
 La base de datos de SSO es la base de datos de SQL Server que almacena la información acerca de las aplicaciones afiliadas, así como de todas las credenciales de usuario cifradas en todas las aplicaciones afiliadas.  
  
 El *servidor secreto principal* es el servidor de Enterprise Single Sign-On que almacena el secreto principal. Todos los servidores de inicio de sesión único (SSO) del sistema obtienen el secreto principal del servidor secreto principal.  
  
 El sistema SSO también contiene uno o más servidores de SSO. Estos servidores llevan a cabo la asignación entre las credenciales de Microsoft Windows y el servidor, además de buscar las credenciales en la base de datos de SSO. Los administradores los utilizan para el mantenimiento del sistema de SSO.  
  
 Para más obtener una visión completa en Enterprise Single Sign-On, vea [descripción SSO](../core/understanding-sso.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura en tiempo de ejecución](../core/runtime-architecture.md)