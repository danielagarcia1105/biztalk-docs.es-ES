---
title: Instalar adaptadores de BizTalk para aplicaciones empresariales | Documentos de Microsoft
description: Requisitos y los pasos de instalación para TIBCO Enterprise Message Service, JD Edwards OneWorld, JD Edwards EnterpriseOne, PeopleSoft Enterprise y TIBCO Rendezvous en BizTalk Server
ms.custom: ''
ms.date: 10/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa1a09f3d9fa531cee51ecd0e94b99ab972ba13
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "23450533"
---
# <a name="install-and-configure-the-microsoft-biztalk-adapters-for-enterprise-applications"></a>Instalar y configurar Microsoft BizTalk Adapters para aplicaciones empresariales 
  
 Microsoft BizTalk Adapters para aplicaciones empresariales incluye los siguientes adaptadores:  
  
-   Adaptador de Microsoft BizTalk para JD Edwards OneWorld  
  
-   Adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne  
  
-   Adaptador de Microsoft BizTalk para PeopleSoft Enterprise  
  
-   Adaptador de Microsoft BizTalk para TIBCO Rendezvous  
  
-   Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service  


> [!IMPORTANT]
> - Realizar una copia de todos los datos antes de realizar los cambios de configuración
> - Debe tener experiencia con la aplicación de empresa específica antes de realizar los cambios de configuración
  
## <a name="supported-versions--requirements"></a>Versiones admitidas y requisitos

||Requisitos|  
|---|---|
|Sistema operativo|El adaptador es compatible con el mismo sistema operativo que BizTalk Server:<ul><li>[Requisitos de BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</li><li>[BizTalk Server 2013 R2 / 2013 requisitos](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)</li></ul>|
|Sistema empresarial compatibles|[Línea de negocio (LOB) y los sistemas empresariales compatibles](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) enumera las versiones admitidas |
|JD Edwards OneWorld XE | <ul><li>Servidor de JD Edwards Enterprise en Windows</li><li>Servidor de implementación de JD Edwards en Windows</li></ul>|
|JD Edwards EnterpriseOne | El adaptador llama a la API de JD Edwards EnterpriseOne que usa JDBC, que necesita un controlador para la base de datos. Si instala JD Edwards EnterpriseOne con una base de datos SQL, necesita controladores MS SQL. De forma similar, si instaló JD Edwards EnterpriseOne con una base de datos de Oracle, se necesita controladores de Oracle; o bien, si instala con una base de datos de DB2, necesita controladores de DB2. |
|PeopleSoft Enterprise | <ul><li>Java Development Kit (JDK) de Sun Systems</li><li>Versión de herramientas de PeopleSoft</li><li>Versión de las aplicaciones de PeopleSoft</li><li>Este adaptador requiere una modificación en la aplicación PeopleSoft. Para usar interfaces de componentes, cargar una interfaz de componente personalizado, GET_CI_INFO, en PeopleSoft. GET_CI_INFO.PC está en archivos de programa\Archivos comunes\Microsoft BizTalk Adapters para Enterprise \Config\.</li></ul>|
|TIBCO Rendezvous | <ul><li>El componente de tiempo de ejecución de TIBCO Rendezvous debe instalarse en el equipo donde se ejecuta el adaptador de BizTalk para TIBCO Rendezvous</li><li>La licencia de TIBCO Rendezvous debe configurarse en el equipo donde se ejecuta el adaptador de BizTalk para TIBCO Rendezvous.</li><li>El directorio de archivos binarios de TIBCO Rendezvous debe ser visible para el adaptador: bien en el valor PATH de las variables de entorno, bien especificado en cada puerto Rendezvous en BizTalk Server. Esto es necesario para que el ensamblado de Rendezvous encuentre sus bibliotecas y ejecutables.</li></ul>|
|TIBCO Enterprise Message Service | Versión de Enterprise Message Service (EMS) 5.x y versiones posteriores incluye un cliente SDK (mediante la API TIBCO EMS C#). El adaptador de BizTalk para TIBCO EMS utiliza para comunicarse con el servidor. |


## <a name="jd-edwards-oneworld-xe"></a>JD Edwards OneWorld XE

Esta sección se incluye información clave sobre el uso de Microsoft BizTalk Adapter para JD Edwards OneWorld XE con BizTalk Server.
  
### <a name="create-the-jar-files"></a>Crear los archivos JAR
 Esta sección describe los requisitos para que JD Edwards OneWorld trabaje con el adaptador de Microsoft BizTalk para JD Edwards OneWorld.  
  
#### <a name="jar-files-and-the-classpath"></a>Archivos JAR y CLASSPATH  
 Archivos JAR de JD Edwards OneWorld deben estar disponibles para el adaptador. Por ejemplo, para conectarse a la versión B7.3.3.3, son necesarios los siguientes archivos jar. Función del servidor que se conecta, puede cambiar la lista de archivos jar:
  
-   Connector.jar    
-   Kernel.jar  
  
 Estos archivos se encuentran en un equipo que ejecuta JD Edwards OneWorld, en las siguientes ubicaciones:  
  
-   JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar    
-   JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar  
  
 Puede copiar estos archivos en cualquier ubicación. Sin embargo, debe especificar la ubicación de los archivos JAR en CLASSPATH. CLASSPATH debe incluir la ruta de acceso completa del archivo y el nombre del archivo JAR (separado por punto y coma).  
  
 El adaptador de BizTalk para JD Edwards OneWorld proporciona el archivo JAR JDEJAccess para su uso con JD Edwards OneWorld. De forma predeterminada, se hace referencia desde el archivo JDEJAccess.jar *archivos de programa\Archivos comunes\Microsoft BizTalk Adapters para Enterprise applications\j. Edwards OneWorld(r)\classes\JDEJAccess.jar*. 
  
> [!NOTE]
>  Debe comprobar el registro del archivo jdeinterop.ini antes de poder utilizar el adaptador de BizTalk para JD Edwards OneWorld. Asegúrese de incluir una ruta de acceso a este archivo en el **propiedades de transporte de JDE** página cuando se crea el puerto de envío de BizTalk Server. Para obtener una explicación completa, vea "Personalizar el archivo jdeinterop.ini."  
  
#### <a name="create-the-btslibinteropjar-file"></a>Crear el archivo BTSLIBinterop.jar  
Crear el archivo y confirme que el adaptador puede tener acceso a ella. Utilice el ejemplo siguiente como guía:  
  
1.  Cree el archivo BTSLIB.cmd que contiene el código siguiente:  
  
    ```  
    define library BTSLIB  
    login  
    library BTSLIB  
    interface JDEAdapter  
    import B5500900  
    build  
    logout  
    ```  
  
2.  Ejecute el siguiente comando:  
  
    ```  
    GenJava  /cmd  .\BTSLIB.cmd  
    ```  
  
### <a name="verify-your-setup"></a>Compruebe la configuración  
  
1.  Usar una versión compatible, incluido el número de service pack ([Supported línea de negocio (LOB) y los sistemas empresariales](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)). Los Service Packs (ESU y ASU) actualizan los archivos binarios del sistema. El requisito previo del Service Pack proporciona la opción de menú ASU/ESU para la importación.  
  
2.  Configurar el archivo jdeinterop.ini para utilizar la unidad correcta para el registro, si es diferente de la unidad C. Por ejemplo, la actualización de JD Edwards OneWorld puede fallar si el directorio TEMP está fuera del espacio.  
  
3.  Determine si debe agregar un archivo de configuración para el margen izquierdo o derecho de los campos de JD Edwards OneWorld.  
  
4.  Compruebe que la variable de entorno JAVA_HOME apunta a la instalación del Kit de desarrollo de Java (JDK) para habilitar los comandos javac y java desde cualquier programa en el equipo.  
  
5.  Compruebe que la variable de entorno CLASSPATH está establecida. Esto permite que el adaptador de BizTalk para JD Edwards OneWorld localizar los archivos Kernel.jar y Connect.jar.  
  
    La ruta de acceso de los archivos JAR distingue mayúsculas de minúsculas.  
  
6.  Pruebe el entorno escribiendo el comando siguiente, que distingue mayúsculas de minúsculas.  
  
    ```  
    javap -s -p com.microsoft.jde.JDEJAccess  
    ```  
  
7.  El comando que proporciona, javap, es el Desensamblador de archivos de clase de Java:  
  
    ```  
    http://java.sun.com/j2se/1.3/docs/tooldocs/solaris/javap.html  
    ```  
  
8.  El `javap` comando desensambla un archivo de clase. El resultado depende de las opciones utilizadas. Si se utiliza ninguna opción, javap imprime el paquete, protegido y campos públicos y métodos de las clases que se pasa a él. el comando javap imprime su salida a stdout.  
  
     Si no hay ningún error, todos los archivos de Java y sus dependencias se encuentran en CLASSPATH.  
  
9. Configurar la resolución de DNS configurando el archivo de host local (*C:\WINNT\system32\drivers\etc\hosts*), con el nombre del servidor del sistema JD Edwards OneWorld.  
  
### <a name="create-and-install-the-custom-package"></a>Crear e instalar el paquete personalizado  
Instalar el paquete personalizado de BTSREL para utilizar el adaptador de BizTalk para JD Edwards OneWorld. Esta sección se describe:  
  
-   El proceso de creación de paquetes personalizados de JD Edwards OneWorld  
-   Cómo crear e instalar BTSREL  
-   Los objetos BTSREL creados en JD Edwards OneWorld
  
> [!NOTE]
>  BTSREL.exe es un paquete personalizado (una actualización de software automatizada o ASU, en la terminología de JD Edwards OneWorld). Contiene funciones de negocio para extraer metadatos. Debe crearse un paquete personalizado para una configuración específica y la versión de JD Edwards OneWorld.  
  
#### <a name="define-a-custom-package"></a>Definir un paquete personalizado  
 Un paquete personalizado es una versión posterior a la entrega que proporciona cambios de software para fines específicos, como los cambios de las disposiciones legales o mejoras. Estos paquetes personalizados se crean para funcionalidades específicas. Por ejemplo, BTSREL se crea para extraer metadatos. Cuando se instala el paquete personalizado de BTSREL, actualiza los módulos seleccionados en el entorno de JD Edwards OneWorld. Para actualizar, se deben combinar objetos BTSREL en el entorno adecuado de JD Edwards OneWorld. Para obtener una lista detallada de los módulos actualizados por BTSREL, consulte la lista de módulos.  
  
#### <a name="install-the-btsrel-custom-package"></a>Instalar el paquete personalizado BTSREL   
Descargar [BTSREL](https://www.microsoft.com/download/details.aspx?id=56113). Instalar en el servidor de implementación y, a continuación, implementarlo en el servidor de empresa.  
  
 El paquete BTSREL.exe existente funciona directamente con la versión B7333. Para que funcionen con la versión de B7334, a continuación, el paquete:  
  
1.  Descargue y extraiga el contenido de BTSREL.exe en la carpeta de trabajo.  
  
2.  Modificar libremente la **ReleaseLevelRequired** y **versión** valores a B7334 en el archivo Deployment.Inf.  
  
3.  Ejecute el programa de instalación.  
  
 Para instalar BTSREL, se requiere lo siguiente:  
  
-   Instalación del servidor de implementación    
-   Plataforma de trabajo de la instalación  
  
#### <a name="install-btsrel-on-the-deployment-server"></a>Instalar BTSREL en el servidor de implementación  
 Personalizado solo funciona en un sistema operativo Windows del paquete y se usa con el servidor de implementación. Se debe basado en el servidor de implementación y, a continuación, se implementa en el servidor de empresa. El servidor de empresa suele ser un servidor de producción y puede estar en el sistema operativo Windows o UNIX.  
  
> [!NOTE]
>  Al aplicar ASU al servidor de implementación de JD Edwards OneWorld, compruebe que se encuentra en **actualización** modo. El **prueba** modo comprueba que no haya errores en ASU, mientras que **actualización** modo está designado para cuando aplique ASU.  
  
1.  Inicie sesión en el servidor de implementación como usuario **JDE**.  
  
2.  Cree una carpeta nueva, llamada BTSREL, en la carpeta Servidor de implementación (raíz) /B7.  
  
3.  Copie BTSREL.exe en la carpeta BTSREL recién creada.  
  
4.  Ejecute BTSREL.exe desde la carpeta .../B7/BTSREL. El Administrador de instalación se inicia automáticamente.  
  
5.  En la ventana de instalación, seleccione **siguiente**y, a continuación, seleccione **finalizar**. Si la instalación se realiza correctamente, aparece un mensaje.  
  
6.  Inicie sesión en el entorno de JDEPLAN como la**JDE** usuario en el servidor de implementación de JD Edwards OneWorld.  
  
    1.  Si la actualización de software electrónica (ESU) que incluye RAE #4533357 no está instalada en el sistema, seleccione **las actualizaciones de Software** desde el **herramientas de instalación del sistema** menú (GH9612).  
  
    2.  Escriba 02 para la opción 1 en el **opciones de procesamiento** panel.  
  
    3.  Si se ha instalado el ESU que incluye RAE #4533357 en el sistema, seleccione **actualización de Software de la aplicación** desde el **herramientas de instalación del sistema** menú (GH9612).  
  
#### <a name="install-btsrel-on-the-jd-edwards-oneworld-workbench"></a>Instalar BTSREL en el área de trabajo de JD Edwards OneWorld  
   
1.  En el **trabajar con la actualización de la aplicación** pantalla, haga doble clic en la actualización BTSREL y, a continuación, seleccione **siguiente**.  
  
2.  Haga doble clic en los entornos donde desea que la actualización instalada y, a continuación, seleccione **siguiente**.  
  
    1.  Comprobar **Workbench desatendida** si desea que la actualización de software para que se ejecute en modo desatendido.  
  
    2.  Seleccione **copia de seguridad** si desea que la copia de seguridad de las especificaciones (de modo que se pueden restaurar las especificaciones originales).  
  
3.  En el **trabajar con el Plan de instalación** pantalla, seleccione el plan para la actualización que se va a instalar, y, a continuación, **seleccione**.  
  
4.  Una vez finalizada la instalación, vea los archivos PDF generados automáticamente para consultar los errores.  
  
    > [!NOTE]
    >  Si se producen errores, busque sugerencias para resolver problemas en la Guía de actualización de software de JD Edwards OneWorld o póngase en contacto directamente con JD Edwards OneWorld.  
  
5.  Registrar manualmente la biblioteca de funciones de negocio mediante los pasos que se incluyen en "Registro manual de la biblioteca de funciones de negocio" en esta sección.  
  
#### <a name="uninstall-the-custom-package"></a>Desinstalar el paquete personalizado  
 No hay ningún requisito para desinstalar el paquete personalizado. Sin embargo, si desea limpiar el sistema, puede desinstalar el paquete de maneras diferentes. Después de desinstalar, vuelva a generar el paquete usando uno de los métodos siguientes:  
  
-   Usar el servidor de implementación de JD Edwards OneWorld, Gh8612 — P96470, en la **fila** menú, seleccione **actualización**y, a continuación, seleccione **desinstalar**.    
-   Consulte todos los objetos personalizados (BTSREL) en un equipo cliente y eliminarlos.    
-   Aplique una instantánea de base de datos anterior.  
  
 Durante la limpieza, compruebe otras modificaciones a otros objetos de JD Edwards OneWorld.  
  
#### <a name="manually-register-the-business-function-library"></a>Registrar manualmente la biblioteca de funciones de negocio  
 Debido a una limitación del proceso de empaquetado del producto de JD Edwards OneWorld, el archivo DLL de la biblioteca de funciones de negocio personalizada para el adaptador de BizTalk para JD Edwards OneWorld debe registrarse manualmente con JD Edwards OneWorld. Este proceso consta de los pasos siguientes.
  
##### <a name="step-1-create-the-custom-business-function-library"></a>Paso 1: Crear la biblioteca de funciones de negocios personalizada  
 Con Object Management Workbench (OMW) de JD Edwards OneWorld, cree la biblioteca de funciones de negocio personalizada. El siguiente procedimiento debe realizarse en la instalación inicial y se aplica a todas las plataformas.  
  
1.  Inicie Object Management Workbench (ruta de acceso rápido: "OMW" o selección del menú: GH902 objeto: P98220).  
  
2.  Seleccione **agregar**y seleccione la opción para **biblioteca de funciones de negocio**.  
  
3.  Escriba la siguiente información para el nuevo objeto de biblioteca de funciones de negocio:  
  
    -   **Nombre:** ACBLIB    
    -   **Descripción:** DLL de Microsoft    
    -   **Código de producto:** 55    
    -   **Código de sistema de producto:** 55  
  
4.  Seleccione **Aceptar**.  
  
##### <a name="step-2-rebuild-libraries-from-the-deployment-server"></a>Paso 2: Volver a generar las bibliotecas desde el servidor de implementación  
Complete los pasos siguientes en la instalación inicial para cada plataforma.  
  
1.  Para iniciar el programa BusBuild en modo independiente, seleccione **iniciar**, seleccione **ejecutar**y, a continuación, seleccione **busbuild.exe**.
  
2.  Inicie sesión en JD Edwards OneWorld en el pathcode (PY7333, PD7333 o DV7333).  
  
3.  En el **volver a generar las bibliotecas** lista, seleccione la **generar**.  
  
##### <a name="step-3-copy-the-custom-dll"></a>Paso 3: Copie el archivo DLL personalizado  
 Copie el archivo DLL personalizado desde el directorio pathcode a los directorios de paquete primario en el servidor de implementación de JD Edwards OneWorld y en el servidor de empresa de JD Edwards OneWorld.
  
**En el servidor de implementación de JD Edwards OneWorld XE**  
  
1.  Copie ACBLIB.dll de DV7333\bin32 a DV7333\Packages\DV7333FA\bin32.  
  
2.  Copie ACBLIB.def, ACBLIB.dmp y ACBLIB.mak de la carpeta DV7333\obj a la carpeta DV7333\Packages\DV7333FA\obj.  
  
3.  Copie ACBLIB.exp, ACBLIB.lib y sACBLIB.lib de DV7333\lib32 a DV7333\Packages\DV7333FA\lib32 carpeta.  
  
**En el servidor de JD Edwards OneWorld Enterprise**  
  
Después de crear cada directorio y archivo, compruebe la autorización.  
  
1.  Cree un directorio ACBLIB en DV7333FA\obj\\.  
  
2.  Cree un directorio ACBLIB en DV7333FA\source.  
  
3.  FTP b5500900.c del directorio del servidor de implementación DV7333\source al directorio DV7333FA\source\ACBLIB.  
  
4.  FTP b5500900.h desde el directorio de implementación servidor DV7333\include al directorio DV7333FA\include.  
  
##### <a name="step-4-build-a-full-package"></a>Paso 4: Crear un paquete completo  
 Debido a una limitación del proceso de compilación del paquete JD Edwards, crear un paquete completo para los entornos a los que se aplicó la actualización BTSREL o la compilación del paquete de actualización no funciona correctamente. Consulte la documentación de JD Edwards sobre cómo crear una compilación del paquete completo.  
  
> [!NOTE]
>  Al aplicar JD Edwards OneWorld como ASU/ESU, ASU/ESU no crea normalmente una nueva biblioteca y las funciones empresariales. Por lo tanto, el proceso es sencillo: sin embargo, el adaptador de BizTalk para el paquete personalizado de JD Edwards OneWorld crea una nueva biblioteca. Por lo tanto, debe realizar pasos adicionales, cree un directorio como manualmente y ejecute una compilación completa del paquete.  
  
#### <a name="modules-list"></a>Lista de módulos  
 El paquete personalizado BTSREL crea los siguientes objetos en JD Edwards OneWorld. BTSREL contiene las funciones de negocio para extraer metadatos y funciones personalizadas para probar los tipos de datos.  
  
> [!NOTE]
>  Hay un error en la actualización de JD Edwards OneWorld. Si no tiene todos los negocios y las funciones personalizadas, compruebe que se ha completado una compilación completa del paquete, en lugar de una compilación del paquete de actualización.  
>  
>  Si faltan archivos en la lista, por ejemplo, si tiene todos los elementos por debajo de ACBTEST y nada por encima de él, puede que le falten los elementos del diccionario de datos (DD). Puede ir a **los elementos de trabajo con datos** y buscar los archivos que faltan.  
>   
>  Si faltan otros elementos, como ACBCHAR01, ACBDATE01, ADBINT01, ACBMATH01 y ACBSTR01, estos son los *elementos de datos principales*. Al combinar objetos de planes a DEV, muchos informes se ejecutan en segundo plano. Puede abrir los informes de combinación y buscar posibles errores. Los informes deben mostrar todos los elementos e indicar que se completaron sin errores o advertencias. Con esta comprobación puede continuar porque se tienen en cuenta todos los elementos.  
  
-   ACBCHAR01: PRUEBA DE CARÁCTER TIPO 01  
  
-   ACBCUST: ID. DE CLIENTE ACB  
  
-   ACBDATE01 - FECHA DE PRUEBA DE TIPO 01  
  
-   ACBDEF: DEFINICIÓN DE TIPO DE FUNCIÓN ACB  
  
-   ACBFCNT: RECUENTO DE LISTA DE NOMBRES DE FUNCIÓN ACB  
  
-   ACBFUNC - LISTA DE NOMBRES DE FUNCIÓN ACB  
  
-   ACBFUNCN - NOMBRE DE LA FUNCIÓN ACB  
  
-   ACBINT01: PRUEBA DE ENTERO TIPO 01  
  
-   ACBLIB: BIBLIOTECA DE CONTROLES DE BROKER  
  
-   ACBMATH01: PRUEBA MATEMÁTICA TIPO 01  
  
-   ACBNEWS: ESTADO NUEVO ACB  
  
-   ACBORDER: NÚMERO DE PEDIDO ACB  
  
-   ACBPRC: PRECIO DE ARTÍCULO ACB  
  
-   ACBPROD: ID. DE PRODUCTO ACB  
  
-   ACBQTY: CANTIDAD DE ARTÍCULOS ACB  
  
-   ACBRES: INDICADOR DE RESULTADO ACB  
  
-   ACBSTAT: ESTADO ACB  
  
-   ACBSTR01: PRUEBA DE CADENA TIPO 01  
  
-   ACBTEST: PRUEBA DE PANTALLA ACB  
  
-   ACBTEST2 - PRUEBA DE PANTALLA ACB 2  
  
-   ACBTEST3 - PRUEBA DE PANTALLA ACB 3  
  
-   B5500900: MÓDULO DE SOPORTE TÉCNICO DE BROKER DE CONTROL  
  
-   D5500900 - ESTRUCTURA DE DATOS DEL AGENTE DE CONTROL  
  
-   D5500900A - ESTRUCTURA DE DATOS DEL AGENTE DE CONTROL  
  
-   D5500900B - ESTRUCTURA DE DATOS DE PRECIOS DE FETCH  
  
-   D5500900C: OBTENER ESTRUCTURA DE DATOS DE ESTADO DE CLIENTE  
  
-   D5500900D - ESTRUCTURA DE DATOS DE ESTADO DE CLIENTE DE SET  
  
-   D5500900E - ESTRUCTURA DE DATOS DE ESTADO DE PEDIDO DE VENTAS DE ACTUALIZACIÓN  
  
-   D5500900F: PRUEBA ENTERO  
  
-   D5500900G - CADENA DE PRUEBA  
  
-   D5500900H - FECHA DE LA PRUEBA  
  
-   D5500900I - CHAR DE PRUEBA  
  
-   D5500900J: PRUEBA MATEMÁTICA NUMÉRICA  
  
-   D5500900K - FECHA DE LA PRUEBA 2  
  
#### <a name="customize-the-jdeinteropini-file"></a>Personalizar el archivo jdeinterop.ini  
 Las clases de conector de JD Edwards OneWorld XE en Connector.jar y Kernel.jar requieren que utilice el archivo de configuración de jdeinterop.ini. Este archivo está definido por el software de JD Edwards OneWorld y usa su terminología. La Guía de interoperabilidad de JD Edwards OneWorld versión puede proporcionar más información sobre el propósito y la terminología de este archivo. Hay un archivo de ejemplo jdeinterop.ini en *< Adapter_Installation > \config\jde*.  
  
Actualizar jdeinterop.ini para que coincida con los valores de parámetro que definió en el **propiedades de transporte** pantalla. Varios sistemas lógicos de JD Edwards OneWorld pueden compartir el mismo archivo jdeinterop.ini si sus parámetros son compatibles. Por lo general, si dos sistemas lógicos apuntan a dos equipos diferentes de JD Edwards OneWorld, necesitan dos copias distintas de jdeinterop.ini.  
  
> [!NOTE]
>  El registro en jdeinterop.ini debe estar desactivado, y los parámetros para los distintos archivos de registro pueden omitir.  
  
 La tabla siguiente detalla la configuración encontrada en el archivo jdeinterop.ini. La información está organizada por secciones. Por ejemplo, [JDENET] y las secciones que se muestran en el orden en que aparecen en el software de JD Edwards OneWorld.  
  
#### <a name="jdeinteropini-file-settings"></a>configuración del archivo jdeinterop.ini
  
|Sección|Parámetro y descripción|  
|-------------|-------------------------------|  
|[JDENET]|**EnterpriseServerTimeout.** El valor de tiempo de espera para una solicitud en el servidor de empresa en milisegundos. El tamaño predeterminado es 120000.<br /><br /> **maxPoolSize.** El tamaño de grupo de conexión de socket JDENET. El tamaño predeterminado es 30.|  
|[SERVER]|**glossaryTextServer.** El servidor de empresa y el puerto que proporcionan información de texto de glosario. Este es el servidor que devuelve las descripciones de texto para los errores. Suele ser los mismos host y puerto que el servidor de aplicación de JD Edwards OneWorld. Puede haber más de un servidor de glosario para las diferentes codificaciones de idioma admitidas. Por ejemplo, JDED:6010 o actsrv1:6009. Los valores deben coincidir con los establecidos en la definición del sistema.<br /><br /> **codePage.** El esquema de codificación. El valor predeterminado es 1252.<br /><br /> -Europeo occidental e inglés de 1252<br /><br /> -Japonés 932<br /><br /> -950 Chino tradicional<br /><br /> -936 Chino simplificado<br /><br /> -Coreano 949|  
|[REGISTROS]|**log= c:\jas.log.** Ubicación del archivo de registro. Puede omitir este parámetro de forma segura.<br /><br /> **debuglog= c:\jasdebug.log.** Ubicación del archivo de registro de depuración. Puede omitir este parámetro de forma segura.<br /><br /> **Debug.** Determina si la depuración de JDENET está activada. El valor predeterminado es FALSE.|  
|[DEBUG]|**JobFile= c:\Interop.log.** La ubicación del archivo de error. Puede omitir este parámetro de forma segura.<br /><br /> **DebugFile= c:\InteropDebug.log.** Ubicación del archivo de depuración. Puede omitir este parámetro de forma segura.<br /><br /> **log= c:\net.log.** Ubicación del archivo de registro. Puede omitir este parámetro de forma segura.<br /><br /> **debugLevel= 0 - 12.** Niveles de depuración. Puede omitir este parámetro de forma segura. Define el nivel de seguimiento proporcionado por el conector de COM y el componente Callobject en el archivo de registro especificado, solo en el servidor COM.<br /><br /> -0 Ninguno. El registro está desactivado y solo los errores se escriben en el archivo JobFile.<br /><br /> -2 errores (mensajes de error)<br /><br /> -4 errores del sistema (mensajes de excepción)<br /><br /> -Información sobre la advertencia 6<br /><br /> -Min 8 seguimiento (operaciones de clave. Por ejemplo, inicio de sesión, cierre de sesión, llamadas de función empresarial)<br /><br /> -Información de solución de problemas de 10 (Ayuda).<br /><br /> -12 información de depuración completa (registra todo)<br /><br /> -De forma predeterminada, no es necesario activar el seguimiento, pero es útil al depurar el código.<br /><br /> - NetTraceLevel=0. Niveles de seguimiento. Puede omitir este parámetro de forma segura. Define el nivel de seguimiento proporcionado por el componente de ThinNet en el archivo de registro especificado en el servidor COM solo. Los valores impares se reservan para agregar futuros niveles.<br /><br /> -La siguiente lista describe aún más los niveles de depuración:<br /><br /> -0 ningún seguimiento<br /><br /> -1 hace referencia el identificador de proceso de registro, Id. de subproceso y el estado de socket disponibles cuando se agrega una nueva conexión y se busca en el grupo de Sockets.<br /><br /> -2 incluye la información en el nivel de seguimiento 1 y también realiza un seguimiento de todas las llamadas efectuadas en la clase del Administrador de conexiones.<br /><br /> -3 incluye toda la información de seguimiento de nivel 2 y también seguimientos las llamadas getPort() y getHost() llamadas.|  
|[INTEROP]|**enterpriseServer.** Este valor es el nombre del servidor host. Asegúrese de que este valor es el mismo valor que escribe en el **nombre de Host** campo el **credenciales de JDE** sección **definición del sistema** en el  **Las propiedades de transporte** cuadro de diálogo. El valor predeterminado es JDED.<br /><br /> **port.** Este valor es el número de puerto que se utiliza para intercambiar datos. Asegúrese de que este valor es el mismo valor que escribe en el **número de puerto** campo JD Edwards **credenciales** sección en la **propiedades de transporte, la definición del sistema**. Por ejemplo, 6010 o 6009. Los valores deben coincidir con los establecidos en **definición del sistema**.<br /><br /> **inactive_timeout**. El valor de tiempo de espera en milisegundos para que una transacción en modo de confirmación automática. Si el usuario está inactivo durante este período de tiempo (en milisegundos), el servidor de interoperabilidad cierra al usuario. Puede cambiar este valor a un período de tiempo menor. El valor predeterminado es 1200000.<br /><br /> **manual_timeout.** El valor de tiempo de espera en milisegundos para una transacción en el modo de confirmación manual. El valor predeterminado es 120000.<br /><br /> **Repository.** Apunta a la ubicación del directorio que contiene Connector.jar y Kernel.jar. En UNIX, se trata de una ruta de acceso completa.|  
|[CORBA]|Puede omitir este parámetro de forma segura.<br /><br /> **Multithread.** Puede omitir la configuración. Establézcalo en 1 para compatibilidad multiproceso con CORBA.<br /><br /> Objects= CORBA::Connector;CORBA::OneWorldVersion<br /><br /> Define los objetos que el servidor CORBA crea durante el inicio. También reemplaza - DIORFILENAME = la opción de línea de comandos, por ejemplo: CORBA::Connector=connector.ior.|  
  
## <a name="jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne  
Esta sección se incluye información clave sobre el uso de Microsoft BizTalk Adapter para JD Edwards EnterpriseOne con BizTalk Server.
  
### <a name="execute-a-jd-edwards-enterpriseone-master-business-function"></a>Ejecutar una función empresarial principal de JD Edwards EnterpriseOne  
 Puede usar el adaptador de BizTalk para JD Edwards EnterpriseOne para invocar una función empresarial principal de JD Edwards EnterpriseOne, como la libreta de direcciones, un pedido de compra o un pedido venta. También puede usar el adaptador como parte de un esfuerzo de integración para conectar JD Edwards EnterpriseOne con BizTalk Server.  
  
##### <a name="access-data-stored-in-jd-edwards-enterpriseone"></a>Acceder a los datos almacenados en JD Edwards EnterpriseOne  
 El adaptador acepta mensajes XML para permitir que las aplicaciones de BizTalk Server comunicarse e intercambiar las transacciones con JD Edwards EnterpriseOne mediante uno de los siguientes:  
  
-   **Adaptador de transmisión**, que usa un puerto de envío de petición-respuesta estático para enviar un mensaje a JD Edwards EnterpriseOne y espera una respuesta.    
-   **Adaptador de recepción**, que usa un puerto de recepción estático unidireccional para recibir mensajes de JD Edwards EnterpriseOne.  
  
### <a name="interoperability-framework"></a>Marco de interoperabilidad  
 JD Edwards EnterpriseOne proporciona integración con sistemas a través de su marco de interoperabilidad. El adaptador utiliza el marco de trabajo de JD Edwards EnterpriseOne y aprovecha las ventajas de la integración de diversos métodos de acceso para proporcionar el máximo grado de flexibilidad y funcionalidad.  
  
 El adaptador de BizTalk para JD Edwards EnterpriseOne admite los siguientes métodos de acceso de integración:  
  
-   JD Edwards EnterpriseOne ThinNet API    
-   JD Edwards EnterpriseOne XML    
-   Tablas de transacciones sin editar de JD Edwards EnterpriseOne (tablas Z)  
  
 El adaptador utiliza la API ThinNet de JD Edwards EnterpriseOne para comunicarse con la aplicación JD Edwards EnterpriseOne. Mediante el uso de la API ThinNet, el adaptador puede invocar una función empresarial principal (MBF) en una sola unidad de trabajo (UOW). Cuando se produce un error en una MBF, se produce un error en toda la UOW. Esto evita las actualizaciones parciales. La validación de datos, las reglas de negocios y las comunicaciones a la base de datos subyacente se administran mediante la aplicación JD Edwards EnterpriseOne.  
  
#### <a name="jd-edwards-outbound-processing-framework"></a>Marco de trabajo de procesamiento de salida de JD Edwards  
 En el proceso de salida, el evento se inicia cuando se ejecuta una MBF específica en el entorno de JD Edwards EnterpriseOne. La MBF escribe la información necesaria para el evento en la tabla de interfaz adecuada y, a continuación, notifica a la función por lotes de subsistema (BF) que se produjo un evento. A continuación, la función BF de subsistema incluye una entrada sobre el evento en la cola de datos del subsistema.  
  
 El subsistema de salida recupera la entrada de la cola de datos y busca en la tabla de control de exportación de datos los procesos externos para notificar. A continuación, el subsistema de salida llama al adaptador de BizTalk para el agente de escucha de JD Edwards EnterpriseOne con la notificación. El agente de escucha pasa la notificación al generador. A continuación, el generador utiliza la API ThinNet de JD Edwards EnterpriseOne para recuperar la información correspondiente de la tabla de interfaz.  
  
### <a name="set-string-justification-in-jdearglist"></a>Conjunto de justificación de cadena en Jdearglist  
 Para configurar determinados argumentos de cadena como justificado a la derecha e izquierda se rellena en el J.D. Archivo jdearglist.txt de Edwards EnterpriseOne, debe saber qué función empresarial que desea tener acceso; en concreto, debe saber qué campos de la función empresarial desea llamar.  
  
 Debe actualizar jdearglist.txt antes de generar los enlaces (esquemas) en la orquestación. Las instrucciones para actualizar el archivo jdearglist.txt que se describen en la sección "Control de valores de cadena".  
  
 Si recibe un mensaje de advertencia de jdearglist.txt en el registro, su finalidad es que le informan de que el archivo jdearglist.txt no existe. Sin embargo, si se ejecuta la función de negocio SalesOrder o PurchaseOrder, debe tener ese archivo en la ruta de acceso o no funciona.  
  
### <a name="understand-jdeinteropini"></a>Comprender jdeinterop.ini  
 Las clases de conector de JD Edwards EnterpriseOne en Connector.jar y Kernel.jar requieren el uso de un archivo de configuración denominado jdeinterop.ini. Este archivo se define por el software de JD Edwards EnterpriseOne y usa su terminología. Para obtener más información sobre el propósito y la terminología de este archivo, consulte a la Guía de interoperabilidad de JD Edwards. Hay un archivo de ejemplo jdeinterop.ini en: archivos de programa\ Microsoft BizTalk Adapters para Enterprise Applications\ J.D. Edwards EnterpriseOne(r)\config.  
  
 No se recomienda modificar este archivo manualmente porque interactúa con el **propiedades de transporte** cuadro de diálogo para el puerto de envío, por ejemplo, los campos marcados como **< configurado por BizTalk\>** .  
  
## <a name="peoplesoft-enterprise"></a>PeopleSoft Enterprise  
Esta sección incluye información clave sobre el uso de Microsoft BizTalk Adapter para PeopleSoft Enterprise con BizTalk Server.
  
### <a name="receive-handler-peoplesoft-requirements"></a>Requisitos de PeopleSoft de controlador de recepción  
 PeopleSoft Integration Broker debe poder comunicarse con BizTalk Server. Es posible que lo siguiente ya haya ocurrido en un entorno PeopleSoft existente y podrá volver a usar un nodo existente. Por lo tanto, no tendrá que hacer nada salvo obtener las especificaciones de HTTP desde un administrador del sistema de PeopleSoft. Para obtener información detallada, consulte la documentación de PeopleSoft.  

Los pasos siguientes proporcionan una introducción a llevar a cabo en PeopleSoft:  
  
1.  Configure el mensaje y actívelo mediante el Diseñador de aplicaciones.  
  
2.  Realice un cambio una sola vez en el archivo integration.gateway.properties de PeopleSoft.  
  
3.  Crear y configurar la puerta de enlace y los nodos para activar HTTP:
  
    -   El nodo debe utilizar algún método desencadenador, por ejemplo, el mecanismo LOCATION_SYNC.   
    -   El nodo debe utilizar HTTP.    
    -   El nodo debe señalar el host y el puerto al que está enviando el evento.  
  
### <a name="send-handler-peoplesoft-requirements"></a>Requisitos de PeopleSoft de controlador de envío  
 El adaptador de BizTalk para PeopleSoft Enterprise consta de una interfaz de componente personalizado (CI) que proporciona acceso a través de una API de Java. Un objeto de elemento de configuración personalizado, **GET_CI_INFO**, se implementa en el sistema PeopleSoft mediante las herramientas de PeopleSoft, para proporcionar información de metadatos requerida por el adaptador de BizTalk para PeopleSoft Enterprise. Para obtener más información, consulte la documentación de PeopleSoft.  
  
 La carga de la interfaz de componente personalizado solo se realiza una vez. Este archivo, GET_CI_INFO.pc, se proporciona con el producto y debe instalarse en el sistema PeopleSoft antes de que pueda usar el adaptador para buscar CI. Debe tener acceso a PeopleSoft Application Designer; Sin embargo, el Diseñador de aplicaciones no tiene que en cualquier lugar cerca del equipo de BizTalk Server. Use el Diseñador de aplicaciones para cargar el CI personalizado en el equipo de PeopleSoft que examinar.  
  
 Debe tener acceso al equipo de PeopleSoft porque debe establecer la variable de entorno CLASSPATH (o establecer la información en el **propiedades de transporte** ventana) para que señale al archivo PeopleSoft PSJOA/psjoa.jar.  
  
### <a name="set-environment-variable-and-use-component-interface"></a>Establecer la variable de entorno y usar la interfaz de componentes  
Para obtener más información acerca de PeopleSoft, consulte la documentación de PeopleSoft.  
  
#### <a name="set-classpath-environment-variable"></a>Establecer la variable de entorno ClassPath  

**Update JAVA_HOME**    
  
 Defina la variable JAVA_HOME para que señale a la instalación de JDK, por ejemplo:  
  
```  
set JAVA_HOME=C:\j2sdk1.4.2_06  
```  
  
 **Actualizar CLASSPATH**  
  
Para usar interfaces de componentes (solo para PeopleSoft 8) debe actualizar CLASSPATH para que incluya la interfaz de componente de PeopleSoft jar de archivo:
  
1.  En **el Panel de Control**, abra **System**.  
  
2.  En el **avanzadas** ficha, seleccione **Variables de entorno**y, a continuación, seleccione **CLASSPATH**.  
  
3.  Agregue la ruta de acceso. Por ejemplo, escriba:  
  
    ```  
    <PeopleSoft_Home>\web\PSJOA\psjoa.jar  
    ```  
  
 El adaptador de BizTalk para PeopleSoft Enterprise requiere el archivo psjoa.jar. Esto se realiza al crear un puerto de envío. Para obtener más información, consulte "Configuración de propiedades de transporte en el sistema PeopleSoft" en la documentación del adaptador.  
  
> [!NOTE]
>  Solo hay uno de estos directorios en su RUTA para asegurarse de que el adaptador de BizTalk para PeopleSoft Enterprise recoge las DLL correctas. Un error al configurar el entorno correctamente para la versión deseada de PeopleSoft podría provocar errores que son difíciles de seguir.  
  
#### <a name="use-component-interfaces"></a>Usar interfaces de componentes  
  
<a name="BKMK_CustomCI"></a>   
##### <a name="upload-a-custom-ci-into-peoplesoft"></a>Cargar un elemento de configuración personalizado en PeopleSoft  
 El adaptador de BizTalk para PeopleSoft Enterprise requiere una modificación de la aplicación PeopleSoft. Para utilizar las interfaces de componentes, debe cargar una interfaz de componentes personalizada, GET_CI_INFO, en PeopleSoft. Solo debe importar GET_CI_INFO durante la instalación inicial para utilizar el adaptador. El adaptador utiliza GET_CI_INFO para obtener información sobre otras interfaces de componentes existentes en PeopleSoft.  
  
 Esta sección explica cómo importar manualmente una interfaz de componente personalizado que le permite examinar las interfaces de componentes de PeopleSoft. Tenga en cuenta que los métodos personalizados no utilizan ni modifican las propiedades de la interfaz de componentes que está instalada. Para importar la interfaz de componentes personalizada, puede utilizar uno de los métodos siguientes:  
  
-   Crear un componente nuevo para importar los métodos personalizados.  
  
-   Utilizar un componente existente que no contiene ninguna clave, por ejemplo, INSTALLATION_RS.  
  
 La interfaz de componentes simple no debe contener claves. Si no está seguro de si una interfaz de componentes determinada contiene claves, puede ejecutar esta instrucción SQL sencilla mediante la herramienta Consulta SQL. Ofrece una lista de todas las interfaces de componente en la aplicación que no tienen claves.  
  
```  
select distinct BCNAME  
from PSBCITEM bc1  
where not exists  
(select 1  
from PSBCITEM bc2  
where bc1.BCNAME = bc2.BCNAME  
and bc2.BCTYPE in (1, 2))  
```  
  
 Puede seguir la documentación de PeopleSoft para crear un único componente simple para almacenar el adaptador de BizTalk para métodos personalizados de PeopleSoft Enterprise. También puede clonar una de las interfaces de componente ya existente y utilizarla para almacenar los métodos personalizados.  
  
 Para comprobar que su GET_CI_INFO no tiene claves, ejecute la herramienta de prueba de la interfaz de componentes del diseñador de aplicaciones de PeopleTools.  
  
<a name="BKMK_NewCom"></a>   
##### <a name="create-a-new-component-interface"></a>Crear una nueva interfaz de componente  
 Siga estos pasos para crear una nueva interfaz de componente con PeopleSoft, Diseñador de aplicaciones:
  
1.  Abra la **Application Designer de PeopleSoft**.  
  
2.  Escriba un tipo de conexión de tres niveles y, a continuación, haga clic en **Aceptar**. Por ejemplo, seleccione Servidor de aplicaciones en la lista.  
  
3.  En el Diseñador de aplicaciones, en la **archivo** menú, seleccione **nuevo**.  
  
4.  En el **New** cuadro de diálogo, seleccione **interfaz de componente**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **Seleccionar**.  
  
6.  En la lista de todos los componentes, seleccione cualquier componente sencillo. Por ejemplo, seleccione INSTALLATION_RS o un nuevo componente de PeopleSoft que haya creado.  
  
 Los métodos personalizados no utilice o modifique las propiedades de la interfaz de componente que se instala en.  
  
 Esta interfaz de componente simple no debe contener claves. Si no está seguro de si una interfaz de componentes determinada contiene claves, puede ejecutar esta instrucción SQL sencilla mediante la herramienta Consulta SQL. Proporciona una lista de todas las interfaces de componente en la aplicación que no tienen claves:  
  
```  
select distinct BCNAME from PSBCITEM bc1 where not exists (select 1 from PSBCITEM bc2 where bc1.BCNAME = bc2.BCNAME and bc2.BCTYPE in (1, 2))  
```  
  
> [!NOTE]
>  También puede seguir la documentación de PeopleSoft para crear un único componente simple para almacenar los métodos personalizados para el adaptador de BizTalk para PeopleSoft Enterprise.  
  
 Para comprobar que su GET_CI_INFO no tiene claves, ejecute la herramienta de prueba de la interfaz de componentes del diseñador de aplicaciones de PeopleTools.  
  
##### <a name="check-component-interface"></a>Compruebe la interfaz de componentes  
 Ha completado la carga del adaptador de Microsoft BizTalk para PeopleSoft GET_CI_INFO en su sistema PeopleSoft. GET_CI_INFO es una interfaz de componentes personalizados definida por el usuario. Contiene métodos definidos por el usuario. La interfaz del componente GET_CI_INFO le permite examinar las interfaces de componentes en su sistema PeopleSoft mediante el asistente para adaptador de Microsoft. Puede localizar y expandir GET_CI_INFO para ver sus métodos definidos por el usuario.  
  
> [!NOTE]
>  Para obtener más información acerca de los métodos definidos por el usuario, vea "Métodos de definidos por el usuario de interfaz de PeopleSoft: componente" en la documentación del adaptador.  
  
##### <a name="set-the-component-interface-security"></a>Establecer la seguridad de la interfaz de componente  
 Después de instalar la interfaz de componente personalizada de PeopleSoft GET_CI_INFO en PeopleSoft, establezca la configuración de seguridad **GetCINamespace**, **GetDetails**, y **GetCollections**métodos para el adaptador de BizTalk para PeopleSoft Enterprise. Se trata de una práctica estándar al crear componentes personalizados o métodos definidos por el usuario.  
  
> [!NOTE]
>  El siguiente procedimiento describe cómo configurar la seguridad de todas las versiones compatibles de PeopleSoft en todos los modos compatibles.  
>   
>  Para configurar la seguridad de la interfaz de componentes  
  
1.  Seleccione **PeopleTools**, seleccione **seguridad**, seleccione **permisos y Roles**y, a continuación, seleccione **listas de permisos**.  
  
2.  En el **mantener la seguridad** ventana, haga clic en **búsqueda**, seleccione la correspondiente **lista de permisos**y, a continuación, haga clic en el hipervínculo de la lista correspondiente.  
  
3.  En el **lista de permisos** panel de la derecha, haga clic en la flecha derecha junto a la **tiempos de inicio de sesión** ficha para mostrar la **Interfaces de componentes** ficha.  
  
4.  Haga clic en el **Interfaces de componentes** ficha.  
  
5.  Haga clic en el signo más (+) para agregar una nueva fila a la **Interfaces de componentes** lista.  
  
6.  Seleccione el **GET_CI_INFO** interfaz de componente y, a continuación, haga clic en **editar**.  
  
7.  Para establecer los métodos en **acceso completo**, haga clic en **acceso completo (todos)** y, a continuación, haga clic en **Aceptar**.  
  
8.  Desplácese hasta la parte inferior de la **Interfaces de componentes** ventana y, a continuación, haga clic en **guardar**.  
  
##### <a name="test-the-component-interface"></a>Probar la interfaz de componente  
 Ha terminado de configurar la seguridad de la interfaz de componentes GET_CI_INFO proporcionada con el adaptador de BizTalk para PeopleSoft Enterprise. La interfaz de componentes de PeopleSoft está lista y puede examinar las interfaces de componentes de PeopleSoft.  
  
 Siga estos pasos para probar la interfaz de componentes en el diseñador de aplicaciones.  
  
 Para probar la interfaz de componentes  
  
1.  Iniciar el **Application Designer de PeopleSoft**.  
  
2.  En el **archivo** menú, elija **abiertos**y, a continuación, seleccione **definición = interfaz de componente**.  
  
3.  En la lista de interfaces de componentes, seleccione **CI GET_CI_INFO**.  
  
4.  Después de abrir GET_CI_INFO, haga clic en cualquier lugar en el panel derecho de la definición de interfaz de componente y, a continuación, seleccione **interfaz de componentes de prueba**.  
  
El **comprobación de la interfaz de componente** abre la ventana. No debería haber ninguna clave indicada. Si su GET_CI_INFO contiene claves, o si no hay otra opción de selección, vuelva al diseñador de aplicaciones y elimine todas las claves de GET_CI_INFO.  
  
## <a name="install-steps"></a>Pasos de la instalación
 Antes de instalar, puede que el servidor BizTalk Server y todos los requisitos previos de software para los adaptadores instalados. Se recomienda que cierre todas las aplicaciones antes de ejecutar el programa de instalación.  
  
1.  Ejecutar el servidor BizTalk Server **Setup.exe**, seleccione **instalar Microsoft BizTalk Adapters**y seleccione **instalar Microsoft BizTalk Adapters para aplicaciones empresariales**.  
  
    > [!NOTE]
    >  - También puede ejecutar una instalación silenciosa con el comando siguiente: msiexec /i < msi\> /qn/l * < archivo de registro\> , donde < archivo de registro\> es opcional, pero es útil si se produce un error en la instalación.  
    >  - La instalación actualiza la variable de entorno PATH. Para asegurarse de que usa las variables correctas, cierre la ventana de comandos de instalación para actualizar las variables.  
  
2.  Acepte la **contrato de licencia**y seleccione **siguiente**.
  
3.  Escriba su **información del cliente**y seleccione **siguiente**.  
  
4.  Seleccione un **completar** o **personalizado** instalación: 
  
    -   **Completa**: instala todos los adaptadores de Microsoft BizTalk para aplicaciones empresariales, todas las características de programa y se utiliza para el tiempo de desarrollo y ejecución.  
  
    -   **Personalizado**: elegir los adaptadores y las características que desea instalar y donde estén instalados.  
  
    Para establecer el destino, seleccione **examinar**y establezca la ruta de instalación.  
  
    Seleccione **siguiente** para continuar.  
  
5. **Instalar**y seleccione **finalizar** cuando haya terminado.  
  
> [!IMPORTANT]
>  Puede encontrar el siguiente error durante la instalación:  
>   
>  `Error 1609. An error occurred while applying security settings. CREATOR OWNER is not a valid user or group`  
>   
>  Para solucionar este error, realice las siguientes acciones y ejecutar la instalación de nuevo:  
>   
>  1. Abra un símbolo del sistema
>  2. Tipo: `net user "CREATOR OWNER" /add`. Esto crea un nuevo usuario llamado CREATOR OWNER.
>  3. Tipo: `net localgroup Users /add`. Esto crea un nuevo grupo denominado usuarios.
  
Para agregar los adaptadores de BizTalk Server, vea "Agregar adaptadores para la administración de BizTalk" en este tema.

## <a name="add-adapters-to-biztalk-admin"></a>Agregar adaptadores a administradores de BizTalk
  
> [!NOTE]
>  Si instala BizTalk en un entorno de varios equipos (instalación solo en tiempo de ejecución en un equipo y una instalación de sólo herramientas de administración en otro equipo), debe instalar a los adaptadores de BizTalk para aplicaciones empresariales en los equipos.  
  
1.  Abra la consola de administración de BizTalk Server, expanda **Microsoft BizTalk Server**y, a continuación, expanda **configuración de plataforma**.  
  
2.  Haga clic en **adaptadores**, seleccione **New**y, a continuación, seleccione **adaptador**.  
  
3.  Escriba un nombre, como **PeopleSoft**.  
  
4.  Seleccione el nombre especificado de la **adaptador** lista y seleccione **Aceptar**.  
   
## <a name="post-install---jd-edwards-oneworld"></a>Posterior a la instalación-JD Edwards OneWorld  
 Microsoft BizTalk Adapter para JD Edwards OneWorld está formada por un adaptador de transmisión que interactúa bases de datos admitidas y sistemas de servidor Microsoft BizTalk Server. El adaptador de transmisión permite invocar la llamada del sistema del servidor de BizTalk Server. La configuración del adaptador de transmisión (el controlador de envío de administración de BizTalk Server) especifica la ubicación de la base de datos SQL.  
  
 Consulte la documentación del adaptador para obtener información acerca de cómo usar el adaptador de BizTalk para JD Edwards OneWorld y la asignación entre su modelo y el servidor BizTalk Server.  
  
### <a name="single-sign-on"></a>Inicio de sesión único  
 El adaptador de BizTalk para JD Edwards OneWorld proporciona soporte técnico para Enterprise Single Sign-On (SSO). Si selecciona usar SSO en el **propiedades de transporte** página, las credenciales para la aplicación afiliada en la base de datos de credenciales de SSO que se usan. Una aplicación afiliada representa una aplicación, es decir, un elemento back-end que requiere credenciales.  
  
### <a name="installed-components"></a>Componentes instalados  

* La instalación del adaptador se instala y registra los componentes siguientes en la caché de ensamblados global (GAC). Puede comprobar el registro, abra la carpeta de ensamblados en el Explorador de (< % WINDIR % > \assembly), o usar el `gacutil /l` desde el símbolo del sistema de Visual Studio:

    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  

  
* btsTask.exe instala e implementa el `Microsoft.BizTalk.Adapters.JDEProperties.dll` archivo a la GAC. Los resultados del registro de implementación de BizTalk Server se encuentran en *\Program BizTalk Adapters for Enterprise applications\jdedeploy. HTML* y **jdeDeploy.xml**.
  
* Archivos específicos del adaptador se instalan en *archivos de programa* y *archivos de programa\Archivos comunes*.  
  
* El `sdk\` se instala en *archivos de programa\Microsoft BizTalk Adapters para Enterprise Applications\ J.D. Edwards OneWorld(r)*.
  
* * Archivos de programa\Microsoft BizTalk Adapters para Enterprise Applications\JD Edwards OneWorld(r)\* contiene los archivos siguientes:  
  
    -   classes\JDEJAccess.jar    
    -   Config\ J.D. Edwards OneWorld(r) \BTSREL.exe    
    -   Config\ J.D. Edwards OneWorld(r) \jdearglist.txt    
    -   Config\ J.D. Edwards OneWorld(r) \jdeinterop.ini  
  
* * Programa programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\Bin\* contiene los archivos siguientes:  
  
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   jdecba.dll  
  
## <a name="post-install---jd-edwards-enterpriseone"></a>Posterior a la instalación-JD Edwards EnterpriseOne  
 El adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne contiene un adaptador de transmisión que interactúa con bases de datos admitidas y sistemas de servidor a BizTalk Server. El adaptador de transmisión permite invocar la llamada del sistema del servidor desde BizTalk Server.  
  
 El adaptador de BizTalk para JD Edwards EnterpriseOne proporciona soporte técnico para Enterprise Single Sign-On (SSO). Si selecciona usar SSO en el **propiedades de transporte** página, las credenciales para la aplicación afiliada en la base de datos de credenciales de SSO que se usan. Una aplicación afiliada representa una aplicación, es decir, un elemento back-end que requiere credenciales.  
  
### <a name="installed-components"></a>Componentes instalados  
* La instalación del adaptador se instala y registra los componentes siguientes en la caché de ensamblados global (GAC). Puede comprobar el registro, abra la carpeta de ensamblados en el Explorador de (< % WINDIR % > \assembly), o usar el `gacutil /l` desde el símbolo del sistema de Visual Studio:
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* Los archivos específicos del adaptador se instalan en el *archivos de programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\Bin* carpeta. Esta carpeta contiene los archivos siguientes:  
  
    -   Jdecba.dll    
    -   Microsoft.BizTalk.Adapters.JDEProperties.dll  
  
* Los siguientes archivos se instalan en *programa de programa\Microsoft BizTalk Adapters for Enterprise applications\j. Edwards EnterpriseOne(r)*:  
  
    -   Bin\BTAJDEEnterpriseOneTrace.cmd    
    -   Classes\JDEDynAccess.jar    
    -   Config\btaJDEEnterpriseOneTrace.mof    
    -   Config\jdearglist.txt    
    -   Config\jdeinterop.ini    
    -   Config\jdelog.properties    
    -   Sdk  
  
 
## <a name="post-install---peoplesoft-enterprise"></a>Posterior a la instalación-PeopleSoft Enterprise  
 Microsoft BizTalk Adapter para PeopleSoft Enterprise contiene un adaptador de transmisión que interactúa bases de datos admitidas y sistemas de servidor a BizTalk Server. El adaptador de transmisión permite invocar la llamada del sistema del servidor desde BizTalk Server. La configuración del adaptador de transmisión (el controlador de envío de administración de BizTalk Server) especifica la ubicación de la base de datos SQL.  
  
 El adaptador de BizTalk para PeopleSoft Enterprise proporciona soporte técnico para Enterprise Single Sign-On (SSO). Si selecciona usar SSO en el **propiedades de transporte** página, las credenciales para la aplicación afiliada en la base de datos de credenciales de SSO que se usan. Una aplicación afiliada representa una aplicación, es decir, un elemento back-end que requiere credenciales.  
  
 La instalación del adaptador incluye ejemplos en el directorio \sdk.  
  
### <a name="installed-components"></a>Componentes instalados  
* La instalación del adaptador se instala y registra los componentes siguientes en la caché de ensamblados global (GAC). Puede comprobar el registro, abra la carpeta de ensamblados en el Explorador de (< % WINDIR % > \assembly), o usar el `gacutil /l` desde el símbolo del sistema de Visual Studio:
  
    -   Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll    

* Archivos específicos del adaptador se instalan en *archivos de programa* y *archivos de programa\Archivos comunes*. Los siguientes archivos se instalan en *archivos de programa\Microsoft BizTalk Adapters para Enterprise Applications\PeopleSoft Enterprise (r)*:
  
    -   bin\BTAPeopleSoftTrace.cmd    
    -   config\btaPeopleSoftTrace.mof    
    -   config\GET_CI_INFO.pc    
    -   config\GET_CI_INFO.pc    
    -   sdk\  
  
* *Programa de programa\Archivos comunes\Microsoft BizTalk Adapters para aplicaciones empresariales* contiene los archivos siguientes:  
  
    -   bin\psosa.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
## <a name="post-install-overview---tibco-rendezvous"></a>Información general de posterior a la instalación - TIBCO Rendezvous  
 Microsoft BizTalk Adapter para TIBCO Rendezvous contiene de recepción y transmisión de funcionalidad que interactuar con las bases de datos admitidas y sistemas de servidor a BizTalk Server.  
  
-   El lado de recepción escucha llamadas salientes del sistema del servidor.  
  
-   El lado de transmisión permite invocar la llamada del sistema del servidor desde BizTalk Server.  
  
 Consulte la documentación del adaptador para obtener información sobre cómo usar Microsoft BizTalk Adapter para TIBCO Rendezvous y acerca de la asignación entre su modelo y el servidor BizTalk Server.  
  
### <a name="installed-components"></a>Componentes instalados  
* La instalación del adaptador se instala y registra los componentes siguientes en la caché de ensamblados global (GAC). Puede comprobar el registro, abra la carpeta de ensamblados en el Explorador de (< % WINDIR % > \assembly), o usar el `gacutil /l` desde el símbolo del sistema de Visual Studio: 
  
    -   Microsoft.BizTalk.Adapters.TibcoRV    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Common    
    -   Microsoft.BizTalk.Adapters.TibcoRV.Service    
    -   Microsoft.BizTalk.Adapters.TibRV.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoEMS    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.Properties    
    -   Microsoft.BizTalk.Adapters.TibcoRVManagement    
    -   Microsoft.BizTalk.Adapters.TibcoRVReceiver  
    -   Microsoft.BizTalk.Adapters.TibcoRVTransmitter  
  
* Archivos específicos del adaptador se instalan en *archivos de programa y archivos de programa\Archivos comunes*. Los siguientes archivos se instalan en *archivos de programa\Microsoft BizTalk Adapters para Enterprise Applications\ TIBCO Rendezvous(r)*:  
  
    -   bin\BTATibcoRVTrace.cmd    
    -   bin\mbaRV.exe    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll    
    -   bin\Microsoft.BizTalk.Adapters.BizUtil.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll    
    -   bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll    
    -   Config\btaTibcoRVTrace.mof    
    -   sdk\  
  
* *Programa de programa\Archivos comunes\Microsoft BizTalk Adapters para aplicaciones empresariales* contiene los archivos siguientes:  
  
    -   bin\tibcorvcba.dll    
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
### <a name="add-tibcorendezvousdll-to-the-gac"></a>Agregar TIBCO. Rendezvous.dll a la GAC  
 El adaptador de BizTalk para TIBCO Rendezvous requiere el **TIBCO. Rendezvous.dll** archivo. La versión mínima necesaria es 1.0.3036.23330 FileVersion, que se incluye con la versión del producto 8.1. El adaptador desencadena una excepción y registra un mensaje adecuado si este ensamblado no está instalado.  
  
 Debe usar enlace tardío para cargar ensamblados para que los ensamblados de TIBCO Rendezvous no producirán un error cuando una versión concreta de la TIBCO. Rendezvous.dll y TIBCO. Módulo Rendezvous.NET no están en el equipo de destino.
  
 **Componente de tiempo de ejecución**  
  
 Compruebe que tiene el componente de tiempo de ejecución de TIBCO Rendezvous instalado en el equipo. El componente de tiempo de ejecución es el único componente que debe instalar al instalar TIBCO Rendezvous.  

1. En un símbolo del sistema de Visual Studio, cambie los directorios a la ubicación de la TIBCO. Archivo Rendezvous.dll. La ruta de acceso de este archivo DLL en la instalación predeterminada de TIBCO Rendezvous es **C:\TIBCO\TIBRV\BIN\TIBCO. Rendezvous.dll**.  
  
2. En el símbolo del sistema, escriba lo siguiente:  
  
```
C:\TIBCO\TIBRV\BIN > gacutil /i TIBCO.Rendezvous.dll
```
  
 Ahora TIBCO. Rendezvous.dll muestra la lista GAC. Para ver la lista, en el Panel de Control, abra **herramientas administrativas**, abra **configuración de Microsoft .NET Framework**y, a continuación, abra **caché de ensamblados**.  
  
## <a name="post-install---tibco-enterprise-message-service"></a>Posterior a la instalación-TIBCO Enterprise Message Service  
 El adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) contiene una funcionalidad de recepción y transmisión que interactúa con bases de datos admitidas y sistemas de servidor a BizTalk Server.  
  
-   El lado de recepción escucha llamadas salientes del sistema del servidor.  

-   El lado de transmisión permite invocar la llamada del sistema del servidor desde BizTalk Server.  
  
 Consulte la documentación del adaptador para obtener información sobre cómo usar el adaptador de BizTalk para TIBCO EMS y sobre la asignación entre su modelo y el servidor BizTalk Server.  
  
### <a name="installed-components"></a>Componentes instalados  
* La instalación del adaptador se instala y registra el `Microsoft.BizTalk.Adapters.TibcoEMS.dll` archivo en la caché de ensamblados global (GAC). Puede comprobar el registro, abra la carpeta de ensamblados en el Explorador de (< % WINDIR % > \assembly), o usar el `gacutil /l` desde el símbolo del sistema de Visual Studio.
  
* Archivos específicos del adaptador se instalan en *archivos de programa* y *archivos de programa\Archivos comunes*. Los siguientes archivos se instalan en *programa de programa\Microsoft BizTalk Adapters for Enterprise applications\tibco Enterprise mensaje r*:  
  
    -   bin\BTATibcoEMSTrace.cmd    
    -   Microsoft.BizTalk.Adapters.TibcoEMS.dll    
    -   Config\btaTibcoEMSTrace.mof    
    -   sdk\  
  
* *Programa de programa\Archivos comunes\Microsoft BizTalk Adapters for Enterprise Applications\bin* carpeta contiene los archivos siguientes:  
  
    -   Microsoft.BizTalk.Adapters.CoreManagement.dll    
    -   Microsoft.BizTalk.Adapters.CoreReceiver.dll    
    -   Microsoft.BizTalk.Adapters.CoreTransmitter.dll  
  
    > [!NOTE]
    >  Debe usar enlace tardío para cargar ensamblados para que los ensamblados de TIBCO EMS no producirá un error cuando una versión concreta de la TIBCO. EMS.dll no está presente en el equipo de destino.  
  
### <a name="add-tibcoemsdll-api-to-the-gac"></a>Agregar TIBCO. EMS.dll API a la GAC  
 El adaptador de BizTalk para TIBCO EMS requiere que se agregue la TIBCO. EMS.dll a la GAC. El adaptador de BizTalk para TIBCO EMS desencadena una excepción y se registra un mensaje adecuado si este ensamblado no está instalado.  
  
1.  Copiar el TIBCO EMS C #API en el equipo de BizTalk.  
  
2.  En un símbolo del sistema de Visual Studio, cambie los directorios a la ubicación del archivo de la API de C#.  
  
3.  En un símbolo del sistema de Visual Studio, escriba lo siguiente:  
  
    ```
    C:\\<TIBCO EMS Folder\>bin> gacutil /i TIBCO.EMS.dll
    ```
  
 TIBCO. EMS.dll ahora se muestra en la lista C:\Windows\assembly. O bien, en el Panel de Control, abra **herramientas administrativas**, abra **Microsoft .NET Framework**y abra **caché de ensamblados** para ver la lista GAC.  
  
 **Limitaciones**  
  
 BizTalk Adapter para TIBCO EMS usa TIBCO. EMS.dll para comunicarse con el servidor. Las siguientes son limitaciones cuando se usa el TIBCO. EMS.dll:  
  
1.  Compresión de mensajes, que permite al cliente de TIBCO EMS enviar mensajes en un formato comprimido a EMS, no está disponible.  
  
2.  Cifrado de mensajes entre el adaptador y el servidor no está disponible. TIBCO. EMS.dll no permite el cifrado SSL mediante las bibliotecas OpenSSL, pero los adaptadores admiten SLL con Tibco.EMS.dll con ProductVersion 5.0 y versiones posteriores.  
  
3.  No se admite la API de administración para EMS.  
  
## <a name="adapter-tracing"></a>Seguimiento del adaptador

### <a name="enable-tracing"></a>Habilitar el seguimiento
 El nombre de archivo utilizado con el seguimiento de Windows es decisión del administrador. La aplicación escribe en el sistema operativo, que omite todos los registros hasta que desee los registros de un determinado sistema back-end. Esto se hace ejecutando adaptadores de BizTalk independientes para el archivo de comandos de las aplicaciones empresariales. Uno de los argumentos para ese comando es el nombre del archivo que se utiliza para capturar la información de seguimiento. Para obtener más información, vea "Eventos de seguimiento de usar Windows" (en este tema).
  
 Instalan los archivos de seguimiento a * \Program adaptadores de BizTalk para aplicaciones empresariales\*.  
  
-   bin\BTATrace.cmd    
-   config\btaTrace.mof  
  
### <a name="use-windows-trace-event"></a>Usar eventos de seguimiento de Windows  
 Los errores de registro de adaptadores, advertencias y mensajes de información al Visor de eventos de Windows. Puede ver mensajes de seguimiento adicionales mediante la herramienta Seguimiento de eventos para Windows (ETW). Cuando está habilitado ETW, crea un archivo *.etl para recibir los mensajes. Este archivo está en formato binario y se debe convertir para poder leerse. Para ello, debe tener una aplicación de consumidor disponible para interpretar el \*archivo .etl, por ejemplo, Windows tracerpt.exe o tracedmp.exe.  
  
### <a name="etw-components"></a>Componentes ETW
  
 Seguimiento de eventos para Windows tiene tres componentes:  
  
* **Aplicación del controlador:** activa y desactiva un proveedor. Por ejemplo, tracelog.exe o logman.exe.  
  
    Configure su variable de entorno PATH para que señale la ubicación de tracelog.exe. Esto garantiza que BTA < nombre del adaptador\>llamadas de seguimiento pueden localizar tracelog.exe en el sistema. De forma predeterminada, BTA < nombre del adaptador\>seguimiento busca la ruta de acceso actual.  
  
    > [!NOTE]
    >  Tracelog.exe está disponible en el SDK de Microsoft y es compatible con los comandos proporcionados por Microsoft BizTalk Adapters para aplicaciones empresariales. Para usar logman.exe, consulte la documentación de logman.  
  
* **Aplicación de consumidor:** lee eventos registrados.  
  
    Para que la aplicación de consumidor pueda leer el evento en el archivo .etl, Seguimiento de eventos para Windows debe volcarlos en dicho archivo. Normalmente esto se realiza cuando el controlador desactiva el seguimiento.  
  
    Para usar la aplicación de consumidor sin desactivar el seguimiento, el controlador debe activar el seguimiento con la opción en tiempo real, **< tiempo Real\> = -rt**.  
  
* **Proveedor:** utiliza para proporcionar el evento.  
  
    Cada adaptador incluye cinco proveedores diferentes. Están registrados en el Instrumental de administración de Windows (WMI). Para encontrar los proveedores registrados en la ruta root\WMI\EventTrace, puede usar herramientas tales como WMI CIM Studio.  
  
    Los cinco proveedores le permiten registrar diferentes tipos de mensajes:  
  
        -   **Receiver Logging Provider**: The <Trace element\> switch is - **receiver**.    
        -   **Receiver CastDetails Provider**: The <Trace element\> switch is - **castDetailsReceive**.    
        -   **Transmitter Logging Provider**: The <Trace element\> switch is - **transmitter**.    
        -   **Transmitter CastDetails Provider**: The <Trace element\> switch is - **castDetailsTransmit**.    
        -   **Management Logging Provider**: The <Trace element\> switch is - **management**.  
  
Para usar ETW, ejecute el comando para el adaptador específico: `BTA<Adapter Name\>Trace.cmd`. Use este comando como sigue:  
  
```  
BTA<Adapter Name>Trace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA<Adapter Name>Trace <Trace element> -stop  
  
```  
  
 Donde:  
  
**< elemento de seguimiento\>**  (obligatorio) es el tipo de proveedor. Las opciones son:  
  
 **-castDetailsTransmit**  
  
 **-transmitter**  
  
 **-castDetailsReceive**  
  
 **-receiver**  
  
 **-management**  
  
 **-iniciar, - detener:** activar o desactivar el proveedor.  
  
 **-cir < MB\>:** tamaño y tipo de archivo. **-cir** es un archivo circular. **< MB\>:** tamaño en megabytes.  
  
 **-seq < MB\>:** tamaño y tipo de archivo. **-seq** es un archivo secuencial. **< MB\>:** tamaño en megabytes.  
  
 **-rt:** activar el modo en tiempo real.  
  
 **Archivo de registro:** nombre del archivo de registro (c:\rtlog.etl es el valor predeterminado).  
  
 Por ejemplo:  
  
```  
BTAXXXTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAXXXTrace -transmitter -stop  
  
```  
  
> [!NOTE]
>  Utilice el comando tracerpt.exe para dar formato a los archivos .etl.  

## <a name="next-steps"></a>Pasos siguientes
* [Adaptador de JD Edwards EnterpriseOne](../core/jd-edwards-enterpriseone-adapter.md)
* [Adaptador de JD Edwards OneWorld](../core/jd-edwards-oneworld-adapter.md)
* [Adaptador de PeopleSoft Enterprise](../core/peoplesoft-enterprise-adapter.md)
* [Adaptador TIBCO Enterprise Message Service](../core/tibco-enterprise-message-service-adapter.md)
* [Adaptador de TIBCO Rendezvous](../core/tibco-rendezvous-adapter.md)
