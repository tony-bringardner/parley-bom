# parley-bom

The bill of materials (BOM) for **Parley**, a family of Java libraries for implementing internet
protocols. It lists versions of the Parley modules that work together, so you can use several of
them without picking a version for each.

## Using it

Import the BOM once, then add Parley modules without versions:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>us.bringardner.parley</groupId>
            <artifactId>parley-bom</artifactId>
            <version>1.0.0</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>

<dependencies>
    <dependency>
        <groupId>us.bringardner.parley</groupId>
        <artifactId>parley-ftp</artifactId>
    </dependency>
    <dependency>
        <groupId>us.bringardner.parley</groupId>
        <artifactId>parley-dns</artifactId>
    </dependency>
</dependencies>
```

Modules a Parley module brings in (parley-core, parley-net, ...) also get the BOM's versions.

## What it covers

parley-core, parley-io, parley-net, parley-files, parley-files-ftp, parley-files-sftp,
parley-files-jdbc, parley-ftp, parley-dns, parley-mail, parley-smtp, parley-imap and parley-pop3.
It lists only Parley's own artifacts, never third-party ones.

## Maintaining it

Each BOM release is a set tested together. When any module's version changes, update its property in
`pom.xml` and release a new BOM.
