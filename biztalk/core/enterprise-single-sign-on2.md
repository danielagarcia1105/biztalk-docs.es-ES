---
title: "Solo inicio de sesión en información general de Enterprise | Documentos de Microsoft"
description: Leer sobre las aplicaciones de affilicate, con vales SSO para procesar los mensajes y administrar SSO en BizTalk Server
ms.custom: 
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2aaab59-8cf7-4848-b71a-e7c8682dd3bd
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f242e11e31de957fee0c6cbf228094f7e40010d
ms.sourcegitcommit: 5e6ef63416e8885a5ee91bd65618a842b3a0cc54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2017
---
# <a name="enterprise-single-sign-on-overview"></a>Single Sign-On información general de Enterprise
Es probable que un proceso empresarial que esté basado en varias aplicaciones distintas tenga que pasar por distintos dominios de seguridad. El acceso a una aplicación en un sistema operativo de Microsoft Windows puede requerir un conjunto de credenciales de seguridad, pero es posible que el acceso a una aplicación en un gran sistema (mainframe) IBM requiera credenciales diferentes, como un nombre de usuario y una contraseña de RACF. Trabajar con esta gran cantidad de credenciales es difícil para los usuarios y puede suponer un reto aún mayor en la automatización de procesos. Para resolver este problema, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye el inicio de sesión único (SSO) empresarial.  
  
 No debe confundirse, esto no es un mecanismo que permite a las personas tienen un inicio de sesión para todas las aplicaciones. Por el contrario, el inicio de sesión único empresarial proporciona un método para asignar un Id. de usuario de Windows a credenciales de usuario que no sean de Windows. Este servicio no soluciona todos los problemas de inicio de sesión empresarial de una organización, pero puede facilitar el trabajo en procesos empresariales que utilizan aplicaciones en varios sistemas.  
  
## <a name="create-affiliate-application-for-non-windows-systems"></a>Crear la aplicación afiliada para sistemas distintos de Windows  
 Para utilizar el inicio de sesión único empresarial, un administrador define aplicaciones afiliadas, cada una de las cuales representa un sistema o aplicación ajeno a Windows. Por ejemplo, una aplicación afiliada puede ser una aplicación CICS que se ejecute en un gran sistema (mainframe) IBM, un sistema SAP ERP que se ejecute en Unix o cualquier otro tipo de software. Cada una de estas aplicaciones tiene su propio mecanismo de autenticación, por lo que requiere sus propias credenciales exclusivas.  
  
 El inicio de sesión único (SSO) empresarial almacena en una base de datos de SSO una asignación cifrada entre el Id. de usuario de Windows de un usuario y sus credenciales en una o varias aplicaciones afiliadas. Cuando este usuario necesita obtener acceso a una aplicación afiliada, puede buscar las credenciales de esa aplicación en la base de datos de SSO mediante un Servidor de inicio de sesión único (SSO). El diagrama siguiente refleja su funcionamiento.  
  
 ![](../core/media/understandingbts-11-esso.gif "UnderstandingBTS_11_ESSO")  
  
 En este ejemplo, una orquestación procesa un mensaje enviado por alguna aplicación a BizTalk Server y lo envía a una aplicación afiliada que se ejecute en un gran sistema (mainframe) IBM. La misión del inicio de sesión único empresarial es garantizar que las credenciales correctas, es decir, el nombre de usuario y la contraseña correspondientes, se envían con el mensaje a la aplicación afiliada.  
  
## <a name="message-processing-with-an-sso-ticket"></a>Procesamiento de mensajes con un vale de SSO  
 Como muestra el diagrama, cuando un adaptador de recepción obtiene un mensaje, el adaptador puede solicitar un vale de SSO del servidor de SSO A (paso 1). Este vale cifrado contiene la identidad de Windows del usuario que realizó la solicitud y un periodo de tiempo en espera. (No se debe confundir con un vale de Kerberos, no es lo mismo.) Después de adquirirlo, se agrega como propiedad al mensaje entrante. El mensaje sigue su ruta normal a través del motor de BizTalk Server, lo que en este ejemplo supone que lo controla una orquestación. Cuando esta orquestación genera un mensaje saliente, dicho mensaje también contiene el vale de SSO adquirido con anterioridad.  
  
 El nuevo mensaje está destinado a la aplicación que se ejecuta en un gran sistema (mainframe) IBM, por lo que debe contener las credenciales apropiadas para que este usuario obtenga acceso a la aplicación. Para obtener estas credenciales, el adaptador de envío se pone en contacto con el servidor de SSO B (paso 2) y le proporciona el mensaje (que contiene el vale de SSO) que acaba de recibir y el nombre de la aplicación afiliada para la que está intentando recuperar las credenciales. Esta operación, llamada redención, hace que el servidor de SSO B compruebe el vale de SSO y busque las credenciales del usuario para la aplicación afiliada (paso 3). El servidor de SSO B devuelve las credenciales al adaptador de envío (paso 4), que las utiliza para enviar un mensaje debidamente autenticado a la aplicación afiliada (paso 5).  
  
## <a name="administering-sso"></a>Administrar SSO  
 El inicio de sesión único empresarial también incluye herramientas de administración para llevar a cabo diversas operaciones. Todas las operaciones realizadas en la base de datos SSO se auditan, por ejemplo, por lo que se proporcionan herramientas que permiten a un administrador supervisar estas operaciones y establecer varios niveles de auditoría. Otras herramientas permiten a un administrador deshabilitar una aplicación afiliada determinada, activar y desactivar una asignación individual para un usuario y llevar a cabo otras funciones. Además, hay una utilidad de cliente que permite a los usuarios finales configurar sus propias credenciales y asignaciones. Al igual que otros componentes de BizTalk Server, el inicio de sesión único empresarial expone sus servicios a través de una API programable. Los creadores de adaptadores de BizTalk Server de otros fabricantes utilizan esta API para obtener acceso a los servicios de inicio de sesión único, y los administradores la pueden utilizar para crear secuencias de comandos para automatizar tareas comunes.  
  
 El ejemplo anterior muestra un uso habitual del inicio de sesión único empresarial, pero también puede configurarse de otras formas. Por ejemplo, una instalación de BizTalk Server más pequeña puede tener sólo un único servidor de SSO, y es posible que utilice el inicio de sesión único empresarial independientemente del motor de BizTalk Server. (Esta tecnología también se incluye con Microsoft Host Integration Server.)  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería de BizTalk Server](../core/the-biztalk-server-messaging-engine.md)   
 [Implementación de Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md)
