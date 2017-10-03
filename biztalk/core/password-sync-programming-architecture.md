---
title: "Arquitectura de programación de sincronización de contraseña | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679edbf1-fb08-4472-b366-3e1d361b20e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb68af3624b19a5a5385902d6a0131cfe28acb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="password-sync-programming-architecture"></a>Arquitectura de programación de sincronización de contraseña
Un adaptador de sincronización de contraseñas utiliza un modelo de extracción para interactuar con el resto del sistema Enterprise Single Sign-On: es decir, el adaptador recibe activamente cambios de contraseña desde el servicio de inicio de sesión único (ENTSSO) empresarial y también desde el sistema ajeno a Windows. De igual manera, el adaptador extrae cambios de contraseñas recibidos de un sistema al otro. Con este modelo, el adaptador interactúa con tres componentes de arquitectura: la arquitectura ENTSSO, el componente aplicación auxiliar de sincronización de contraseñas (PS) y un sistema ajeno a Windows especificado.  
  
## <a name="enterprise-single-sign-on-architecture"></a>Arquitectura de inicio de sesión único (SSO) empresarial  
 ENTSSO es el servicio que implementa la tecnología de inicio de sesión único (SSO) empresarial y se ejecuta como un servicio local en el mismo sistema que lo hace el adaptador. Por lo tanto, la comunicación entre el adaptador y ENTSSO siempre es local. No obstante, el adaptador de sincronización de contraseñas se ejecuta en un proceso separado del servicio ENTSSO.  
  
 ENTSSO utiliza el almacén de configuración para almacenar información de configuración para un adaptador. La cuenta de usuarios de aplicación de una aplicación de almacenamiento de configuración corresponde a la cuenta de acceso. Cuando un adaptador llama a ENTSSO, ENTSSO comprueba que éste está dentro de la cuenta de acceso configurada para tal adaptador. La cuenta de acceso tiene que ser una cuenta de grupo (local o de dominio).  
  
 Dado que ENTSSO almacena información de un adaptador, éste puede autoidentificarse en ENTSSO por su nombre de adaptador. El nombre de adaptador corresponde al nombre de la aplicación de almacenamiento de configuración y al identificador de almacenamiento de configuración utilizados para almacenar las propiedades del adaptador. Por lo tanto, los adaptadores solo tienen que conocer su nombre de adaptador para obtener acceso a la información de configuración y para autoidentificarse correctamente en el sistema ENTSSO en tiempo de ejecución.  
  
## <a name="password-sync-helper"></a>Aplicación auxiliar de sincronización de contraseñas  
 La Aplicación auxiliar de sincronización de contraseñas (PS) es un componente COM que proporciona ENTSSO. La Aplicación auxiliar de sincronización de contraseñas (PS) se ejecuta en curso con el adaptador de sincronización de contraseñas y expone ISSOPSWrapper. El adaptador puede llamar a la interfaz para comunicarse con el servicio ENTSSO. La Aplicación auxiliar de sincronización de contraseñas (PS) pasa comunicaciones desde y hacia ENTSSO mediante llamada ligera a procedimiento remoto (LRPC) cifrada (con privacidad de paquetes). Aunque las comunicaciones se realizan principalmente para actualizar contraseñas, también puede utilizar las interfaces para pasar otros tipos de notificaciones entre el adaptador y ENTSSO. Dado que la Aplicación auxiliar de sincronización de contraseñas se ejecuta como un valor singleton por proceso, es posible que muchos adaptadores llamen al mismo objeto de Aplicación auxiliar de sincronización de contraseñas desde el mismo proceso del adaptador. Para obtener más información acerca de cómo utilizar la aplicación auxiliar de sincronización mediante programación, vea [sincronizar contraseñas](../core/synchronizing-passwords.md).  
  
## <a name="non-windows-system"></a>Sistema ajeno a Windows  
 El sistema ajeno a Windows es el equipo remoto con el que interactúa el adaptador. A usted le corresponde decidir cómo interactuar con el sistema ajeno a Windows.  
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de sincronización de contraseña](../core/password-sync-adapters.md)