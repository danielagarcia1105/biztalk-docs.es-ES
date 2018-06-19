---
title: Cómo agregar un certificado a una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, certificates
- managing [certificates], adding to applications
- certificates, applications
- managing [applications], certificates
- managing [certificates], applications
- managing [resources], certificates
ms.assetid: 7c615002-6627-4134-9c2b-bf1c89d626c2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7551e18b1e63f706dfe7e5ff8f951e7aee4f4694
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248180"
---
# <a name="how-to-add-a-certificate-to-an-application"></a>Cómo agregar un certificado a una aplicación
En este tema se describe cómo utilizar la línea de comandos para agregar un certificado a una aplicación de BizTalk. Esta opción no está disponible en la consola de administración de BizTalk Server. Puede agregar un certificado a una aplicación de BizTalk, de modo que pueda transportar el certificado de un grupo de BizTalk a otro, empaquetado con una aplicación. Puede usar certificados para comprobar identidades y establecer vínculos seguros para los puertos de envío y las ubicaciones de recepción. Para obtener más información, consulte [cómo asignar un certificado a un puerto de envío](../core/how-to-assign-a-certificate-to-a-send-port.md) y [cómo asignar un certificado a una ubicación de recepción](../core/how-to-assign-a-certificate-to-a-receive-location.md).  
  
 Al agregar un certificado a una aplicación, tenga en cuenta que los siguientes puntos son importantes:  
  
-   Cuando agregue un certificado a una aplicación, el certificado se agrega a la base de datos de administración de BizTalk como un artefacto de certificado. Cuando instale la aplicación, el certificado se importa en el almacén de certificados Otras personas del equipo local, por lo que es posible que no necesite realizar la importación en este almacén antes de que pueda asignarlo a un puerto de envío o a una ubicación de recepción. Cuando use BTSTask para agregar el certificado, éste debe existir en el almacén de certificados Otras personas y debe especificar la huella digital.  
  
    > [!NOTE]
    >  Cuando se exporta un certificado, se quita la clave privada. Cuando está instalada la aplicación, aunque se importe el certificado en el almacén de certificados, no se podrá usar para descifrar un mensaje cifrado; sí se podrá usar, en cambio, para enviar un mensaje cifrado. Si necesita usar el certificado para el propósito anterior, debería volver a instalarlo en el almacén de certificados Otras personas del equipo que aloja el puerto de envío que usa el certificado.  
  
-   Si una ubicación de recepción o un puerto de envío va a utilizar un certificado en dos o varias aplicaciones, se recomienda implementar el certificado en una aplicación diferente y, a continuación, hacer referencia a esta aplicación desde las aplicaciones que necesitan utilizar el certificado. Esto se debe a que en un grupo de BizTalk solo puede existir un certificado que tenga una huella digital determinada, por lo que no podrá importar el mismo cerificado de dos aplicaciones diferentes. Si intenta importar dos aplicaciones que utilicen el mismo certificado, la primera importación se realizará correctamente, pero la segunda no. En este caso, la utilización de la opción Sobrescribir importación no soluciona el problema, ya que otra aplicación contiene el certificado existente que desea sobrescribir.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-add-a-certificate-to-an-application"></a>Para agregar un certificado a una aplicación  
  
1.  Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **BTSTask AddResource** [**/ApplicationName:***valor*] **/Type:System.BizTalk:Certificate** [**/Overwrite**] **/Thumbprint: "***valor***"** [**/Server:***valor*] [**/Database:***valor*]  
  
     Ejemplo:  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Certificate /Overwrite /Thumbprint: "04 8e a2 32 24 f9 a 36 b9 42 81 12 71 3a d2 ef db c7 9C 83 dc" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ ApplicationName**|Nombre de la aplicación de BizTalk a la que se agrega el certificado. Si no se especifica el nombre de aplicación, se utiliza la aplicación predeterminada de BizTalk para el grupo. Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").|  
    |**/ Tipo**|**System.BizTalk:Certificate** (este valor no distingue entre mayúsculas y minúsculas).|  
    |**/ Sobrescribir**|Opción para actualizar un certificado existente. Si no se especifica y ya existe un certificado en la aplicación que tiene la misma propiedad Huella digital que el certificado que se agrega, se produce un error en la operación Agregar. Puede ver la propiedad Huella digital si hace doble clic en el certificado del complemento Certificados y si hace clic en la pestaña Detalles. Para obtener más información, consulte la sección acerca de información de certificado de la documentación del complemento Certificados.|  
    |**/ Huella digital**|Propiedad de huella digital del certificado (una *huella digital* es una síntesis de datos). Este valor se debe incluir entre comillas dobles (").|  
    |**/ Servidor**|Nombre del servidor SQL Server que aloja la base de datos de administración de BizTalk en el formato Nombredelservidor\Nombredeinstancia,Puerto.<br /><br /> Sólo se necesita el nombre de instancia cuando el nombre de instancia es diferente del nombre de servidor. Sólo se necesita el puerto cuando el servidor SQL Server utiliza un nombre de puerto diferente al predeterminado (1433)<br /><br /> Ejemplos:<br /><br /> Servidor = MyServer<br /><br /> Servidor = MyServer\MySQLServer,1533<br /><br /> Si no se proporciona, se utiliza el nombre de la instancia de SQL Server que se ejecuta en el equipo local.|  
    |**/ Base de datos**|Nombre de la base de datos de administración de BizTalk. Si no se especifica, se utiliza la base de datos de administración de BizTalk que se ejecuta en la instancia local de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource (comando): certificado](../core/addresource-command-certificate.md)   
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)