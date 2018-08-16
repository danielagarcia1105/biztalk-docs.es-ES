---
title: 'Paso 4: Habilitar SSL en IIS | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Socket Layers
- IIS
- double action tutorial, enabling SSL in IIS
- SSL
ms.assetid: 96109294-595a-46ac-974e-33123df79ed5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be53660b5632450d8fa8cb38480c9b728d460bad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009165"
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a>Paso 4: Habilitar SSL en IIS
Capa de Sockets seguros (SSL) es un protocolo que se han diseñado para proteger el canal de comunicación entre un cliente y un servidor. Al habilitar SSL en Microsoft® Internet Information Services (IIS) 7.5 o 7.0, las organizaciones de Contoso y Fabrikam comunican mediante la autenticación y cifrado para todas las transferencias de datos. En este paso, obtendrá información sobre cómo habilitar SSL en IIS 7.5 o 7.0.  
  
> [!NOTE]
>  Tendrá que realizar este paso en los equipos de Contoso y Fabrikam.  
  
### <a name="to-prepare-a-new-server-certificate"></a>Para preparar un nuevo certificado de servidor  
  
1. Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2. En el panel izquierdo de Internet Information Services, expanda **\<** <em>computer_name</em> **\>** (*ordenador*), expanda **sitios Web**, haga clic en **sitio Web predeterminado**y, a continuación, haga clic en **propiedades**.  
  
3. En el cuadro de diálogo de sitios Web predeterminados en el **seguridad de directorios** , haga clic **certificado de servidor** para iniciar el **Asistente para certificados IIS**.  
  
4. En el **éste es el Asistente para certificados de servidor Web** página, haga clic en **siguiente**.  
  
5. En el **certificado de servidor** página, seleccione **crear un nuevo certificado**y, a continuación, haga clic en **siguiente**.  
  
6. En el **Petición demorada o inmediata** página, haga clic en **siguiente**.  
  
7. En el **nombre y la configuración de seguridad** página, haga clic en **siguiente**, mantener los valores predeterminados.  
  
8. En el **información de la organización** página, en el **organización** , escriba **Contoso** if en el equipo de Contoso o **Fabrikam** si está habilitada la Equipo de Fabrikam, en el **unidad organizativa** , escriba **prueba**y, a continuación, haga clic en **siguiente**.  
  
9. En el **nombre común de su sitio Web** página, en el **nombre común** , escriba el nombre del equipo y, a continuación, haga clic en **siguiente**.  
  
10. En el **información geográfica** página, en el **estado o provincia** , escriba su estado o provincia, en el **ciudad o localidad** , escriba la ciudad o localidad y, a continuación, haga clic en **Siguiente**.  
  
11. En el **nombre de archivo de solicitud de certificado** página, en el **nombre de archivo** cuadro, deje el valor predeterminado **C:\certreq.txt**y, a continuación, haga clic en **siguiente**.  
  
12. En el **resumen del archivo de petición** página, haga clic en **siguiente**.  
  
13. En el **completar el Asistente para certificados de servidor Web** página, haga clic en **finalizar** para cerrar el **Asistente para certificados IIS**.  
  
### <a name="to-generate-a-new-server-certificate"></a>Para generar un nuevo certificado de servidor  
  
1.  En el \<procesar una solicitud pendiente*página, en el*ruta de acceso y nombre de archivo\> , escriba  unidad: \Certs\SSLCert.cer (o vaya a ese archivo) y, a continuación, haga clic en siguiente.  
  
    > [!NOTE]
    >  En el \<página puerto SSL *, haga clic en* siguiente\>.  
  
2.  En el **resumen del certificado** página, haga clic en **siguiente**.**  
  
3.  En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.  
  
4.  En el **completar el Asistente para certificados de servidor Web** página, haga clic en **finalizar**.  
  
5.  En el **enviar una solicitud de certificado o una solicitud de renovación** página, haga clic en **buscar un archivo insertar**.  
  
    > [!NOTE]
    >  Si recibe un error de seguridad al hacer clic en el vínculo, abra el archivo C:\certreq.txt en el Bloc de notas u otro editor de texto, copie el contenido del archivo y pegar esa información en el **Guardar solicitud** cuadro y, a continuación, haga clic en  **Enviar**. A continuación, puede ir al paso 10.  
  
6.  Haga clic en **examinar** para abrir el **Elegir archivo** cuadro de diálogo.  
  
7.  En el **Elegir archivo** diálogo cuadro, busque la  *\<unidad\>*: \ carpeta, seleccione el archivo certreq.txt y, a continuación, haga clic en **abierto**.  
  
8.  En el **enviar una solicitud de certificado o una solicitud de renovación** página, haga clic en **lectura**.  
  
9. En el **enviar una solicitud de certificado o una solicitud de renovación** página, haga clic en **Submit** para generar el nuevo certificado.  
  
10. En el **certificado emitido** página, haga clic en **Descargar certificado**.  
  
11. En el **de descarga del archivo** cuadro de diálogo, haga clic en **guardar**.  
  
12. En el **Guardar como** cuadro de diálogo, guarde el certificado a \<unidad\>: \Certs\SSLCert.cer y, a continuación, haga clic en **guardar**.  
  
13. Haga clic en **cerrar** para cerrar el **descarga completa** cuadro de diálogo.  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a>Para preparar un nuevo certificado de servidor para IIS  
  
1.  Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el panel izquierdo de Internet Information Services, haga clic en < nombre_equipo > (equipo local), haga doble clic en **certificados de servidor** en el panel derecho. Seleccione **crear solicitud de certificado** desde el panel de acciones.  
  
3.  En el cuadro de diálogo Propiedades de nombre distintivo, escriba el nombre del equipo en el nombre común: cuadro de texto, en la organización:, escriba **Contoso** if en el equipo de Contoso o **Fabrikam** if en Fabrikam equipo en la unidad organizativa: tipo de prueba, en el cuadro de la ciudad o localidad, escriba la ciudad o localidad, en el cuadro de estado o provincia, escriba su estado o provincia, en el país o región desplegable, seleccione su país o región y, a continuación, haga clic en **siguiente**.  
  
4.  En el cuadro de diálogo Propiedades del proveedor de servicios criptográficos, haga clic en **siguiente**.  
  
5.  En el cuadro de diálogo Nombre de archivo, especifique C:\certreq.txt en el cuadro de texto, haga clic en **finalizar**.  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a>Para generar un nuevo certificado de servidor para IIS  
  
1.  En Internet Explorer, busque y abra http://<contoso_machine>/CertSrv.  
  
    > [!NOTE]
    >  En el paso 1, abra http://<contoso_machine>/CertSrv en el equipo de Contoso o Fabrikam.  
  
2.  En la página principal del Asistente para Microsoft Certificate Services, haga clic en **solicitar un certificado**.  
  
3.  En la página solicitar un certificado, haga clic en **solicitud de certificado avanzada**.  
  
4.  En la página de solicitud de certificado avanzada, haga clic en **enviar una solicitud de certificado** por mediante un archivo CMC o PKCS n º 10 codificado en base 64, o enviar una solicitud de renovación mediante un archivo PKCS #7 codificado en base 64.  
  
5.  Abra el archivo C:\certreq.txt en el Bloc de notas u otro editor de texto, copie el contenido del archivo y pegar esa información en el **Guardar solicitud** cuadro en el envío de una página de solicitud de certificado o la solicitud de renovación y, a continuación, haga clic en **Enviar**.  
  
6.  En la página certificado emitido, haga clic en **Descargar certificado**.  
  
7.  En el cuadro de diálogo descarga de archivos, haga clic en **guardar**.  
  
8.  En el cuadro de diálogo Guardar como, guardar el certificado \<unidad\>: \Certs\SSLCert.cer y, a continuación, haga clic en **guardar**.  
  
### <a name="to-import-the-server-certificate-into-iis"></a>Para importar el certificado de servidor en IIS  
  
1.  Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el panel izquierdo de Internet Information Services, haga clic en **(equipo local)**, haga doble clic en **certificados de servidor** en el panel derecho. Seleccione **solicitud de certificados completa** desde el panel de acciones.  
  
3.  En el tipo de cuadro de diálogo Especificar respuesta de la entidad emisora de certificados  **\<unidad\>: \Certs\SSLCert.cer** en **nombre de archivo que contiene la respuesta de la entidad de certificación** cuadro de texto. En el tipo de cuadro de texto Nombre descriptivo **ContosoSSLCert**.  
  
### <a name="to-enable-ssl-bindings-for-iis"></a>Para habilitar a los enlaces SSL para IIS  
  
1.  Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2.  En el panel izquierdo de Internet Information Services, expanda **(equipo local)**, expanda **sitios**, haga clic en **sitio Web predeterminado**y, a continuación, haga clic en **editar Enlaces**.  
  
3.  En el cuadro de diálogo enlaces de sitio, haga clic en **agregar**. En el cuadro de diálogo Agregar enlace de sitio, seleccione **https** en la lista desplegable Tipo, seleccione **ContosoSSLCert** en SSL certificate desplegable, haga clic en **Aceptar**, haga clic en **cerrar** .  
  
### <a name="to-import-the-server-certificate-into-iis"></a>Para importar el certificado de servidor en IIS  
  
1. Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.  
  
2. En el panel izquierdo de Internet Information Services, expanda **\<** <em>computer_name</em> \> (*ordenador*), expanda **Web Sitios**, haga clic en **sitio Web predeterminado**y, a continuación, haga clic en **propiedades**.  
  
3. En el cuadro de diálogo Propiedades del sitio Web predeterminado, en el **seguridad de directorios** , haga clic **certificado de servidor** para iniciar el **Asistente para certificados IIS**.  
  
4. En el **éste es el Asistente para certificados de servidor Web** página, haga clic en **siguiente**.  
  
5. En el **Internet Information Services (IIS) Manager**, expanda **sitios Web**, expanda el **sitio Web predeterminado**, haga clic en PendingTransactions y, a continuación, haga clic en Propiedades.  
  
6. En el **procesar una solicitud pendiente** página, en el **ruta de acceso y nombre de archivo** , escriba  **\<unidad\>: \Certs\SSLCert.cer** (o vaya a ese archivo) y, a continuación, haga clic en **siguiente**.  
  
7. En el **página puerto SSL**, haga clic en **siguiente**.  
  
8. En el **resumen del certificado** página, haga clic en **siguiente**.  
  
9. En el **completar el Asistente para certificados de servidor Web** página, haga clic en **finalizar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de la solución de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)