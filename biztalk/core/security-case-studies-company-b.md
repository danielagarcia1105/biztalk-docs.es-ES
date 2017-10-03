---
title: "Casos prácticos de seguridad: La compañía B | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 48bbb347-919a-435e-b7b1-34a4c0e65e59
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef0e37d4acda263822a2cf06095f2c8fd9989afe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-company-b"></a>Casos prácticos de seguridad: La compañía B
La compañía B es una empresa de software. Su modelo de negocio se basa en transacciones electrónicas con proveedores y clientes clave. La compañía B usa una implementación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para sus transacciones.  
  
 Usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar transacciones y las comunicaciones entre aplicaciones internas y externas. Se comunica con 85 aplicaciones internas y 2300 socios comerciales (aproximadamente). Actualmente procesa aproximadamente 2,5 millones de documentos al mes, pero estima que a finales de 2007 llegará a procesar 6 millones de documentos mensualmente.  
  
## <a name="potential-threats-and-security-concerns"></a>Aspectos relacionados con la seguridad y posibles amenazas  
 La compañía B quiere asegurarse de que sólo va a recibir y procesar mensajes cuyo origen esté autenticado. La compañía B también desea asegurarse de que puede recibir y recuperar documentos procedentes del exterior de su red corporativa de la forma más segura posible. El servidor de seguridad que separa la red corporativa de la compañía B de Internet sólo deja pasar tráfico de los puertos 80 y 443. El firewall rechaza todo el tráfico restante.  
  
## <a name="security-architecture"></a>Arquitectura de seguridad  
 En la ilustración siguiente, se muestra la arquitectura que utiliza la compañía B. La compañía B utiliza BizTalk Server como agente de mensajes para la comunicación entre las aplicaciones internas y para procesar y enviar mensajes con el formato correcto a sus proveedores y clientes, y recibir mensajes de éstos. La compañía B tiene que procesar documentos internos y externos con diferentes formatos, incluidos los archivos sin formato y los documentos XML.  
  
 **Figura 1 arquitectura de seguridad de la compañía B**  
  
 ![La arquitectura de la compañía B](../core/media/bpi-cp-pc-company-b.gif "BPI_CP_PC_COMPANY_B")  
  
 La compañía B utiliza un único servidor de seguridad para separar sus equipos corporativos de Internet. Como nivel de seguridad adicional, la compañía B incorpora la seguridad del protocolo de Internet (IPsec) para la comunicación entre todos los servidores y estaciones de trabajo que se encuentran dentro de la red corporativa. La compañía B utiliza IPsec para cifrar todas las comunicaciones dentro de su dominio interno.  
  
 La compañía B utiliza un servidor de recursos compartidos de archivos para recibir archivos sin formato. Este servidor de recursos compartidos se encuentra fuera del dominio y la red de la empresa. Un servidor de seguridad separa el servidor de recursos compartidos de archivos de la red corporativa. Los socios externos de la compañía B publican sus documentos como archivos sin formato en el servidor de recursos compartidos de archivos y se comunican con éste a través de un Protocolo de túnel punto a punto (PPTP). La compañía B protege el acceso al servidor de recursos compartidos de archivos mediante contraseñas de socio que caducan cada 30 días.  
  
 La compañía B ha creado una aplicación personalizada para el traslado de archivos que recupera los documentos sin formato del servidor de recursos compartidos de archivos y los envía a BizTalk Server para someterlos a un procesamiento adicional. Las aplicaciones internas de la compañía B también utilizan esta aplicación personalizada para pasar archivos sin formato a BizTalk Server. BizTalk Server transforma estos documentos y los envía a los socios comerciales de la compañía B.  
  
 Antes de transformar los datos del socio en formatos de aplicación internos, BizTalk Server comprueba si disponen de entradas para el remitente, el receptor y el tipo de documento. Si BizTalk Server recibe un mensaje que no tiene entradas de remitente, receptor o tipo de documento, lo rechazará. El equipo de operaciones de la compañía B se encargará de analizar el mensaje. Las aplicaciones internas envían mensajes en diversos formatos (EDIFACT, archivo sin formato, XML y ANSI X12).  
  
 La compañía B también recibe documentos de origen interno y externo a través de HTTPS. Los asociados externos publican sus documentos en un servidor Web que se encuentra fuera de la red corporativa. Un servidor de seguridad separa este servidor Web de la red corporativa. La aplicación personalizada para el traslado de archivos también recupera los documentos publicados a través de HTTPS. La compañía B utiliza un producto de terceros para cifrar y firmar los mensajes dirigidos a sus socios comerciales. Como medida de seguridad adicional, se realiza una auditoría nocturna en todos los servidores para asegurarse de que la configuración de seguridad es correcta. Se registran todas las excepciones para revisarlas.  
  
## <a name="see-also"></a>Vea también  
 
 [Casos prácticos de seguridad para pequeñas y medianas empresas](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)