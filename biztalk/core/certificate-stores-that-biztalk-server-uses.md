---
title: Almacenes de certificados que utiliza BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public key certificates
- certificate stores, warnings
- private key certificates
- certificates, private key
- Other People stores [certificates]
- certificate stores, Personal store
- Personal store [certificates]
- certificate stores, Windows stores
- certificates, public key
- certificates, certificate stores
- certificate stores
ms.assetid: 29b65913-be3b-45d9-9865-02e52e4370f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b142ff5b9c9007a86b09acd25f53f8c88796988c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233804"
---
# <a name="certificate-stores-that-biztalk-server-uses"></a>Almacenes de certificados que BizTalk Server usa
BizTalk Server utiliza dos tipos de almacén de certificados: Otras personas, para claves públicas, y Personal, para cada cuenta de servicio de instancia de host para la clave privada.  
  
 **Almacén de certificados otras personas.** Los certificados de clave pública son, como su nombre indica, públicos y accesibles para cualquier persona que use el equipo donde se almacenan. BizTalk Server utiliza los certificados de clave pública para cifrar mensajes a entidades específicas y para comprobar las firmas digitales de mensajes entrantes de entidades específicas. Windows proporciona el almacén de certificados Otras personas para permitirle almacenar los certificados de clave pública utilizados en el equipo. Todos los usuarios pueden leer los certificados de ese almacén, y los administradores de Windows tienen permisos para mantenerlo.  
  
> [!NOTE]
>  Debe guardar los certificados de clave pública en el almacén de certificados Equipo local\Otras personas del equipo local en que reside una instancia de host de BizTalk que se utiliza para comprobar la firma o cifrar mensajes enviados a un socio remoto.  
  
 La siguiente ilustración muestra el almacén de certificados Otras personas usado por BizTalk Server para certificados de clave pública:  
  
 ![Almacén de certificados de otras personas](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")  
  
 **Almacén de certificados personales.** BizTalk Server usa certificados de clave privada para descifrar mensajes entrantes y para firmar mensajes de salida. Cada cuenta de Windows habilitada para iniciar sesión de forma interactiva en un equipo tiene un almacén de certificados personal con el sistema operativo al que solo ella tiene acceso. BizTalk Server utiliza el almacén de certificados personal de cada una de las cuentas de servicio de instancia de host para tener acceso a los certificados de clave privada a los que tiene acceso cada cuenta de servicio. Sólo los propietarios del almacén de certificados pueden tener acceso a sus almacenes de certificados personales y mantenerlos. En otras palabras, debe iniciar una sesión en cada equipo que vaya a alojar canalizaciones de descodificación de S/MIME como cada cuenta de servicio de host, e importar el certificado de descifrado al almacén de certificados personal mediante el complemento Certificados.  
  
 La siguiente ilustración muestra el almacén de certificados Personal usado por BizTalk Server para certificados de clave privada:  
  
 ![Almacén de certificados del usuario actual](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")  
  
> [!IMPORTANT]
>  Los certificados de clave privada deben guardarse en el almacén de certificados Usuario actual\Personal para cada cuenta de servicio de instancia de host en cada equipo que tenga un BizTalk ejecutando una instancia de host que requiera el certificado para descifrado o para la firma de mensajes de salida.  
  
> [!NOTE]
>  Una vez agregado el certificado con la clave privada al almacén de certificados personal de las cuentas de servicio que firmarán mensajes de salida, también debe especificar ese certificado de firma en la consola de administración de BizTalk. Para obtener más información, consulte [cómo configurar BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).  
  
> [!NOTE]
>  El almacén de certificados personal también se denomina almacén de certificados MY cuando se utiliza para operaciones de programación tales como la creación de secuencias de comandos para importar y exporta certificados.  
  
 En la tabla siguiente se describen los certificados que debe instalar en cada almacén de certificados de Windows.  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a>Tabla 1 Certificados para cada almacén de certificados de Windows  
  
|**Propósito del certificado**|**Tipo de certificado**|**Almacén de certificados**|  
|-----------------------------|--------------------------|---------------------------|  
|Firma|Clave privada propia|Almacén personal para cada cuenta de servicio de una instancia de host que tiene una canalización de envío con un componente de canalización de codificador de MIME/SMIME configurado para firmar mensajes (**agregar certificado de firma al mensaje** propiedad establecida en `True`). Para obtener más información, vea [cómo configurar BizTalk Server para enviar mensajes firmados](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)|  
|Comprobación de firma|Clave pública del socio|Almacén Otras personas en cada equipo que tiene una instancia de host que posee una canalización de recepción con un componente de canalización Descodificador de MIME/SMIME. Para obtener más información, consulte [cómo configurar BizTalk Server para recibir mensajes firmados](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).|  
|Descifrado|Clave privada propia|Almacén Personal para cada cuenta de servicio de una instancia de host que tiene una canalización de recepción con un componente de canalización Descodificador de MIME/SMIME. Para obtener más información, consulte [cómo configurar BizTalk Server para recibir mensajes cifrados por](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md).|  
|Cifrando|Clave pública del socio|Almacén otras personas de cada equipo que tenga una instancia de host que tiene una canalización de envío con un componente de canalización de codificador de MIME/SMIME configurado para cifrar mensajes (**habilitar el cifrado** propiedad establecida en `True)`. Para obtener más información, consulte [cómo configurar BizTalk Server para enviar mensajes cifrados con](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md).|  
|Resolución de entidades|Clave pública del socio|Almacén Otras personas del equipo de administración desde el que se está configurando la resolución de entidades. Para obtener más información, consulte [con certificados para la resolución de entidades](../core/using-certificates-for-party-resolution.md).|  
  
 La siguiente ilustración muestra los certificados que necesitará en cada almacén de certificados de un BizTalk Server dedicado a recibir mensajes.  
  
 ![Certificados necesarios para recibir mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
 La siguiente ilustración muestra los certificados que necesitará en cada almacén de certificados de un BizTalk Server dedicado a enviar mensajes.  
  
 ![Certificados necesarios para enviar mensajes seguros](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
 Para obtener más información acerca de los almacenes de certificados y el complemento Certificados de la consola de administración de Microsoft (Microsoft Management Console, MMC), busque "consola de certificados" en la Ayuda de Windows.  
  
## <a name="see-also"></a>Vea también  
 [Certificados que utiliza BizTalk Server para mensajes firmados](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [Certificados que utiliza BizTalk Server para los mensajes cifrados](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [Cifrado y certificados de firma](../core/encryption-and-signing-certificates.md)   
 [Implementación de la seguridad de mensaje](../core/implementing-message-security.md)