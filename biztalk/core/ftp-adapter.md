---
title: Adaptador de FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4663fa2615803b50bd8d9172c599665a787ecc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008461"
---
# <a name="ftp-adapter"></a>Adaptador de FTP
El adaptador de FTP intercambia datos entre un servidor FTP y Microsoft BizTalk Server, y permite la integración de datos imprescindibles almacenados en una gran variedad de plataformas con aplicaciones de líneas de negocios. El adaptador se puede conectar con el servidor FTP a través de un servidor proxy SOCKS4 o SOCKS5.  
  
 El adaptador de FTP puede transferir un gran número de archivos desde un servidor FTP a BizTalk Server. También puede transferir archivos como parte de una orquestación.  
  
 El adaptador de FTP consta de dos adaptadores: un adaptador de recepción y un adaptador de envío.  

En esta sección se describen los adaptadores de recepción y envío FTP, y se ofrece información de seguridad y de prácticas recomendadas.  
  
 ## <a name="receive-adapter"></a>Adaptador de recepción  
  
 El adaptador de recepción FTP permite mover datos desde un servidor FTP a un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Las características clave incluyen:  
  
- Extracción de archivos del servidor FTP a petición.  
  
- Ejecución de sondeos según una programación configurable  
  
- Realización de sondeos del servidor FTP y envío de datos directamente al servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Especificación del servidor FTP como dirección IP, puerto, contraseña y nombre de host.  
  
- Garantiza la entrega de archivos  
  
   El adaptador de recepción FTP también trabaja con la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el explorador de BizTalk para configurar y administrar cada función de recepción, que se compone de los siguientes elementos de configuración:  
  
- Intervalo de sondeo para ejecutar un comando FTP (por ejemplo, 60 minutos).  
  
- Información con la que se enruta el documento a una ubicación de recepción o a un puerto de envío de BizTalk específico.  
  
> [!NOTE]
>  El adaptador de recepción FTP no admite la recepción de archivos desde un conjunto de datos con particiones.  
  
## <a name="send-adapter"></a>Adaptador de envío  
  
 El adaptador de envío FTP permite mover datos desde un servidor FTP a un servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Las características clave incluyen:  
  
-   Capacidad para efectuar envíos a petición  
  
-   Entrega garantizada  
  
## <a name="supported-platforms"></a>Plataformas compatibles  
Información de acceso almacenada en un servidor FTP en cualquiera de las siguientes plataformas:  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)] 2016

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)] R2
  
- [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
- [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2008  
  
- [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 2000 Service Pack 3 (SP3) y posterior  
  
- Sun Solaris 9.0  
  
- HP-UX  
  
- LINUX (Redhat 7.x)  
  
- IBM z/OS v1.9 (MVS)  
  
- IBM O/S 390 que ejecuta MVS  
  
- AS/400 OS/400 V5R1  
  
- i5/OS V5R4 (AS400)  
  
- i5/OS V6R1 (AS400)  
  
- GXS ICS  
  
- AIX  
  
  Se admiten todos los Service Packs, a menos que se indique específicamente.  
  
## <a name="in-this-section"></a>En esta sección  
  
[Procedimientos recomendados y recomendaciones para el adaptador de FTP](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[Configurar el adaptador de FTP](../core/configuring-the-ftp-adapter.md)  

[Propiedades y esquema de propiedades del adaptador de FTP](../core/ftp-adapter-property-schema-and-properties.md)