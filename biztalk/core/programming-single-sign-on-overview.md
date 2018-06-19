---
title: Información general de inicio de sesión único de programación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0a3978-cdbf-4703-9d1d-23e0f4923c9c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5f8ffa7463e4c1fbdd7231cf87abea751fea3d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264828"
---
# <a name="programming-single-sign-on-overview"></a>Información general de inicio de sesión único de programación
Un proceso empresarial apoyado en diferentes aplicaciones probablemente necesite afrontar el reto de trabajar con distintos dominios de seguridad. El acceso a una aplicación en un sistema operativo de Microsoft Windows puede requerir un conjunto de credenciales de seguridad, mientras que el acceso a una aplicación en un gran sistema (mainframe) IBM puede requerir credenciales diferentes. Trabajar con esta gran de credenciales es difícil para los usuarios y puede suponer un desafío aún mayor para automatizar los procesos. Para resolver este problema, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye el inicio de sesión único (SSO) empresarial. SSO permite asignar un Id. de usuario de Windows a credenciales de usuario de otros sistemas. Este servicio puede facilitar los procesos empresariales que utilizan aplicaciones en sistemas diversos.  
  
 Para usar el SSO, un administrador define las aplicaciones afiliadas, cada una de las cuales representa un sistema o aplicación ajenos a Windows. Una aplicación afiliada puede ser una aplicación de sistema de control de información del cliente (CICS) que se ejecute en un gran sistema (mainframe) IBM, un sistema SAP ERP que se ejecute en Unix o cualquier otro tipo de software. Cada una de estas aplicaciones tiene su propio mecanismo de autenticación, por lo que requiere sus propias credenciales exclusivas.  
  
 SSO almacena una asignación cifrada entre el Id. de un usuario de Windows y las credenciales asociadas de una o más aplicaciones afiliadas. Estos pares vinculados se almacenan en una base de datos de SSO. SSO usa la base de datos de SSO de dos maneras. La primera de ellas, denominada *iniciado por Windows Single Sign-On*, usa el identificador de usuario para determinar a qué aplicaciones afiliadas tiene acceso el usuario. Por ejemplo, una cuenta de usuario de Windows podría vincularse a credenciales que den acceso a una base de datos DB2 que se ejecute en un servidor AS/400 remoto. El segundo método, denominado *iniciado por host Single Sign-On*, actúa de forma contraria: determinar qué aplicaciones remotas tienen acceso a un identificador de usuario especificado y los privilegios asociados con esa cuenta. Por ejemplo, una aplicación remota podría vincularse a credenciales que den acceso a una cuenta de usuario que tenga privilegios de administración en una red de Windows.  
  
 Tenga en cuenta que el SSO también incluye herramientas de administración para realizar varias operaciones. Todas las operaciones efectuadas en la base de datos de SSO se auditan; por ejemplo, se proporcionan herramientas que permiten al administrador supervisar estas operaciones y establecer varios niveles de auditoría. Otras herramientas permiten a un administrador deshabilitar una aplicación afiliada particular, activar y desactivar una asignación individual para un usuario y llevar a cabo otras funciones. Además, hay un programa cliente que permite a los usuarios finales configurar sus propias credenciales y asignaciones.  
  
 Uno de los requisitos administrativos para el inicio de sesión único (SSO) es que el sistema local conozca las credenciales necesarias para iniciar sesión en un sistema remoto. Del mismo modo, el sistema remoto debe conocer las credenciales del sistema local. Por lo tanto, cuando actualice sus credenciales, como por ejemplo la contraseña en el equipo local, también debe informar a los sistemas remotos de que lo ha hecho. El componente que diseña para sincronizar contraseñas en toda una empresa se llama un *adaptador de sincronización de contraseña*.  
  
## <a name="in-this-section"></a>En esta sección  
 [Interfaz de inicio de sesión único](../core/single-sign-on-interface.md)  
  
 [Aplicaciones de inicio de sesión único](../core/single-sign-on-applications.md)  
  
 [Lo que debe saber antes de programar el inicio de sesión único](../core/what-you-should-know-before-programming-single-sign-on.md)  
  
 [Plataformas admitidas para el inicio de sesión único](../core/supported-platforms-for-single-sign-on.md)