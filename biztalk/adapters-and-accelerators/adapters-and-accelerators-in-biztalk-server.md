---
title: Adaptadores y aceleradores de BizTalk Server | Documentos de Microsoft
description: Información general de todos los adaptadores y aceleradores de BizTalk, incluidos los adaptadores integrados, BAP, HL7, Swift, RosettaNet, FileAct e InterAct
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7f26a1-e47b-4323-b9f0-58842c55a6f8
ms.author: mandia
ms.openlocfilehash: 30afb33621ed50af010c45edfb2643a24feaf91a
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014179"
---
# <a name="adapters-and-accelerators-in-biztalk-server"></a>Adaptadores y aceleradores de BizTalk Server
 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]incluye diferentes adaptadores y aceleradores para crear aplicaciones que reciben datos y envían datos a distintos servicios y sistemas de LOB. 
 
Esta sección describen los distintos adaptadores y aceleradores disponibles con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

## <a name="out-of-the-box-adapters"></a>Adaptadores de fábrica
Al instalar BizTalk Server, también se instalan a los adaptadores integrados que están listos para usarse. Algunos de estos adaptadores incluyen archivo, FTP, MQ Series, Bus de servicio, las aplicaciones lógicas, POP3, SharePoint y más.

**[Usar adaptadores](../core/using-adapters.md) se enumeran todas ellas y también se muestra cómo usar cada adaptador.**
 
## <a name="biztalk-adapter-pack"></a>BizTalk Adapter Pack
El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]y proporciona adaptadores basados en WCF para conectar su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Oracle, SAP, Siebel y SQL Server. También puede crear sus propios adaptadores basados en WCF mediante el [!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)]. 

**Vea [BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md) para instalar y configurar estos adaptadores, paso a través de tutoriales y escenarios, crear aplicaciones que utilizan los distintos adaptadores y hacerse una idea de cómo basadas en WCF services procese mensajes.**

## <a name="adapters-for-enterprise-applications"></a>Adaptadores para aplicaciones empresariales
Estos adaptadores se incluyen con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Utilice estos adaptadores para conectar el servidor BizTalk Server con JD Edwards EnterpriseOne, JD Edwards OneWorld, PeopleSoft Enterprise, TIBCO Enterprise Message Service y TIBCO Rendezvous.

**Vea [el adaptador de BizTalk para aplicaciones empresariales](biztalk-adapters-for-enterprise-applications.md) para instalar y configurar estos adaptadores, paso a través de tutoriales y escenarios, crear aplicaciones que utilizan los distintos adaptadores y mucho más.** 


## <a name="fileact-and-interact"></a>FileAct e interactuar
El [!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)] se incluyen con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y proporcionar conectividad entre el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] y la sociedad para red de IP de seguros de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo (SIPN). 

El adaptador de FileAct proporciona exchange segura y confiable de archivos y la información relativa a esos archivos. 

El adaptador de InterAct proporciona exchange segura y confiable de los mensajes individuales estructurados financieros. 

**Vea [FileAct e InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md) para instalar y configurar estos adaptadores, recorre algunos escenarios y los tutoriales paso a paso y obtener un buen conocimiento de la arquitectura.** 

## <a name="hl7"></a>HL7

El [!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)] se incluye con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y proporciona conectividad entre el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] y aplicaciones para equipos sanitaria basadas en el estándar de siete de nivel de mantenimiento (HL7).

**Vea [HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md) para instalar y configurar el adaptador, paso a través de varios tutoriales y escenarios, obtenga información acerca de cómo funciona el adaptador y usar las distintas características, incluidos los esquemas, confirmaciones, procesamiento por lotes, validación y mucho más.**

## <a name="rosettanet"></a>RosettaNet
El Acelerador de BizTalk para RosettaNet (BTARN) se incluye con BizTalk Server y simplifica el desarrollo e implementación de soluciones de integración basada en estándares de RosettaNet. BTARN admite RosettaNet Implementation Framework (RNIF); que es un marco de aplicación de red abierta que permite a los socios comerciales en colaboración ejecutar procesos de interfaz de socio (PIP) RosettaNet. 

**Vea [RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md) para obtener más información sobre este acelerador y su uso con las soluciones de BizTalk Server.** 

## <a name="swift"></a>SWIFT
El [!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)] se incluye con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y proporciona conectividad entre el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] y la sociedad para todo el mundo bancos vinculados financieros telecomunicaciones (SWIFT) de formatos de mensajes.

Uso del adaptador con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], clientes, socios y los integradores de sistema pueden simplificar el desarrollo, implementación y compatibilidad de las soluciones de integración para procesos de negocio y la infraestructura de la aplicación del servicios financieros principales.

**Vea [SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md) para instalar y configurar el adaptador, paso a través de algunos tutoriales y utilizar la reparación de mensajes, respuesta FIN y artefactos FRR y mucho más.**

## <a name="get-some-help"></a>Obtener ayuda 
Obtener ayuda y ayudar a otras personas en la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] foros en [http://go.microsoft.com/fwlink/p/?LinkId=87695](http://go.microsoft.com/fwlink/p/?LinkId=87695).