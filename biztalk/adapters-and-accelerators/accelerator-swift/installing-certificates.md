---
title: Instalación de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, installing
- installing, certificates
ms.assetid: 7525f771-623c-420f-99ca-c834e819829d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 111bd267bc7d0bc12d582c3b74846b8874ed8b4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012549"
---
# <a name="installing-certificates"></a>Instalación de certificados
Para enviar, reparar o enviar mensajes, debe tener instalados los certificados apropiados. Este tema describe cómo agregar certificados. En un entorno de producción, consulte el departamento de TI para los certificados.  

 **Resumen**  

 Esta sección proporciona instrucciones sobre cómo crear y almacenar los certificados siguientes:  

- Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta Personal de los certificados - usuario actual y la reparación de mensajes en cada equipo cliente  

- Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta de otras personas de los certificados (equipo Local) y la reparación de mensajes en cada equipo de orquestación de BizTalk server  

- Certificado de entidad de certificación en la carpeta entidades emisoras raíz de confianza en el almacén de certificados (equipo Local) en cada equipo cliente  

  Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también tiene un servidor de certificados instalado en el mismo equipo, deberá excluir el servidor de certificados de las rutas de acceso administrados para Microsoft SharePoint Server.  

  Esta sección contiene:  

- [Agregar certificados al almacén de certificados en el cliente](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  

- [Agregar certificados al almacén de certificados en el servidor](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  

- [Exclusión de CertSrv de las rutas de acceso administradas en la implementación de un solo equipo](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)
