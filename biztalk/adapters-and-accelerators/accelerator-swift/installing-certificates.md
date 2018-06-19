---
title: Instalación de certificados | Documentos de Microsoft
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
ms.openlocfilehash: f5ded26548303dfe9c9a095c24396b4e2683ca4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209468"
---
# <a name="installing-certificates"></a>Instalación de certificados
Para enviar, reparar o enviar mensajes, debe tener instalados los certificados apropiados. En este tema se describe cómo agregar certificados. En un entorno de producción, consulte el departamento de TI para los certificados.  
  
 **Resumen**  
  
 Esta sección proporciona instrucciones sobre cómo crear y almacenar los certificados siguientes:  
  
-   Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta Personal de los certificados - usuario actual y la reparación de mensajes en cada equipo cliente  
  
-   Almacén de certificados para cada uno de los roles de nuevo envío en la carpeta de otras personas de los certificados (equipo Local) y la reparación de mensajes en cada equipo de servidor de la orquestación de BizTalk  
  
-   Certificado de la entidad de certificación en la carpeta entidades emisoras raíz de confianza en el almacén de certificados (equipo Local) en cada equipo cliente  
  
 Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también un servidor de certificados instalado en el mismo equipo, debe excluir el servidor de certificados de las rutas de acceso administradas para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] servidor de SharePoint.  
  
 Esta sección contiene:  
  
-   [Agregar certificados al almacén de certificados en el cliente](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-client.md)  
  
-   [Agregar certificados al almacén de certificados en el servidor](../../adapters-and-accelerators/accelerator-swift/adding-certificates-to-the-certificates-store-on-the-server.md)  
  
-   [Exclusión de CertSrv de rutas de acceso administradas en la implementación de una solo equipo](../../adapters-and-accelerators/accelerator-swift/excluding-certsrv-from-managed-paths-on-a-single-computer-deployment.md)