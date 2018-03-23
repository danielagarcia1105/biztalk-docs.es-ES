---
title: Orígenes y los almacenes de certificados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ade897bb51850b4ef9dd6b530f5fc04c6b2601
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="certificate-sources-and-stores"></a>Orígenes de certificados y almacenes
Este tema describe dónde desea importar certificados desde y dónde se almacenarán los certificados.  
  
## <a name="certificate-sources"></a>Orígenes de certificado  
 Importar certificados de los siguientes archivos:  
  
-   Certificados privados de archivos .pfx o. p12. Después de importar los certificados, almacene estos archivos de forma segura. Si importa los certificados privados mediante la utilidad CertWizard, puede establecer la **/Exportable** cambie a `False`, que es la configuración predeterminada, por lo que no se puede exportar los certificados privados de la tienda en un archivo. Si establece la **/Exportable** cambie a `True`, puede exportar estos certificados en un archivo de los certificados [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC).  
  
-   Certificados públicos de archivos .cer o .der. Socios envían sus certificados para que en estos archivos.  
  
-   Certificados raíz de los archivos .cer o .der. Entidades de certificación envían sus certificados raíz para que en estos archivos.  
  
## <a name="certificate-storage"></a>Almacenamiento de certificados  
 Importar certificados a uno de los dos almacenes de certificados en el equipo local. Almacenar certificados pública en el **certificados (equipo Local)** almacenar. Puede abrir los nodos de este almacén abriendo el **certificados (equipo Local)** nodo en el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console. Puede tener acceso a la **certificados (equipo Local)** almacenar si tiene permisos administrativos en el equipo. Almacenar certificados pública en las siguientes carpetas:  
  
-   Inicio certificados pública en la carpeta Personal en el **certificados (equipo Local)** almacenar  
  
-   Socios certificados pública en la carpeta de otras personas de la **certificados (equipo Local)** almacenar  
  
-   Certificados de entidades emisoras de certificados en la carpeta de la entidad de certificación raíz de confianza de la **certificados (equipo Local)** almacenar  
  
 Almacenar certificados privada en el **certificados - usuario actual** almacenar. Puede abrir los nodos de este almacén, abra la consola de administración utilizando la **runas** comando con el usuario de cuenta de servicio de host. Para obtener más información, consulte [importar certificados](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md).  
  
## <a name="see-also"></a>Vea también  
 [Importación de certificados mediante la utilidad CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)   
 [Importación de certificados mediante MMC](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)   
 [Importación de certificados &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)