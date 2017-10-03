---
title: "Configuración de programación del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e908b3ac79970b917e1e7964868b3b9d5bd852d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-programming-configuration"></a>Configuración de programación del adaptador
Todos los tipos de adaptador de sincronización de contraseñas poseen diferentes requisitos de configuración en función de los sistemas ajenos a Windows para los que diseñe el adaptador. Al igual que en el caso de las aplicaciones afiliadas, puede utilizar el almacenamiento de configuración de inicio de sesión único (SSO) empresarial para almacenar propiedades de configuración de manera central y más segura.  
  
 Como ocurre con el resto de aplicaciones de almacenamiento de configuración, un administrador puede utilizar la interfaz de usuario de administración de inicio de sesión único (SSO) empresarial para ubicar y leer un archivo XML que describe las propiedades de configuración para el adaptador. Las herramientas de administración utilizan el archivo XML para presentar una página de propiedades que reúna los valores de propiedades necesarios para el adaptador específico. También puede usar ISSOConfigStore para cargar y leer combinaciones de nombre/valor XML desde y hacia el almacén de configuración, o puede utilizar la herramienta SSOPS.  
  
 También puede utilizar las herramientas de administración de inicio de sesión único (SSO) empresarial para habilitar o deshabilitar un adaptador. En el momento de la creación, el adaptador está deshabilitado.  
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de sincronización de contraseña](../core/password-sync-adapters.md)