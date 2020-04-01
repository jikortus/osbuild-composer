# OSBuild Composer - Operating System Image Composition Services

## CHANGES WITH 9:

        * Fedora is now build with updates and modules repositories
         enabled, therefore up-to-date images are now produced.
         
        * A new man-page `osbuild-composer(7)` with high-level
         description of the project is now available. It can be built
         by the new man target in the Makfile.
         
        * All Fedora images have now a generic initramfs. This should
         make the images more reproducible and less likely failing to boot
         if the image build was done in a less usual environment.
         
        * Metalink is now used to access the Fedora repositories. This change
         should hopefully lead to more stable builds.

        * Composer is now released to Fedora 32 and 33 in a new
         osbuild-composer package. The old golang-github-osbuild-composer
         package will be automatically upgraded to the new one.

        * The internal osbuild-pipeline command now has a more user-friendly
         interface.

        * The RCM API (in development, experimental) is reworked to allow
         any distribution-architecture-image type combination.

        * The work on a high-level description of image types began.
         See image-types directory.
         
        * The osbuild-worker arguments are reworked, they are now much more
         flexible.
         
        * The image-info tool used in the integration tests can be now run
         on Fedora 32.
         
        * The unit test coverage is now much bigger, thanks to all
         contributors!
         
        * Internal distribution representation is significantly reworked,
         this simplifies the process of adding the support for all currently
         missing architectures.
         
        * Integration tests were also improved, the image tests are fully
         switched to the new Go implementation and an automatic way
         of generating test cases is added. The weldr API coverage is also
         much better. Several bugs in it were fixed in the process.
         
        * Codecov.io is now used to monitor the test coverage of the code.
         
        * As always, minor fixes and improvements all over the place.

        Contributions from: Alexander Todorov, Brian C. Lane, David
                            Rheinsberg, Jacob Kozol, Jakub Rusz, Jiri
                            Kortus, Lars Karlitski, Martin Sehnoutka,
                            Ondřej Budai, Tom Gundersen

        - Liberec, 2020-04-01

## CHANGES WITH 8:

        * All generated pipelines now use the `org.osbuild.rpm` stage of
          *osbuild*, rather than `org.osbuild.dnf`. This improves on splitting
          resource acquisition from image building and should make image
          composition more reliable and faster.

        * The `STATE_DIRECTORY` environment variable now allows changing the
          state directory path of `osbuild-composer`. This is to support older
          systemd versions that do not pass in `StateDirectory=` to the service
          executable.

        * Minor fixes and improvements all over the place.

        Contributions from: Alexander Todorov, Brian C. Lane, Jacob Kozol, Jakub
                            Rusz, Lars Karlitski, Major Hayden, Martin
                            Sehnoutka, Ondřej Budai, Tom Gundersen

        - Berlin, 2020-03-18

## CHANGES WITH 7:

        * Support for `RHEL 8.1` as image type is now available.

        * Semantic versioning of blueprints in the lorax API is now enforced.
          This was always the case for the original lorax API, and *Composer*
          now follows this as well.

        * Lots of internal improvements, including many automatic tests,
          improved error handling, better cache directory management, as well
          as preparations to move over from `org.osbuild.dnf` to
          `org.osbuild.rpm` in all build pipelines.

        Contributions from: Alexander Todorov, Brian C. Lane, Jacob Kozol, Lars
                            Karlitski, Major Hayden, Ondřej Budai, Tom Gundersen

        - Berlin, 2020-03-05

## CHANGES BEFORE 7:

        * Initial implementation of 'osbuild-composer'.

        Contributions from: Alexander Todorov, Brian C. Lane, Christian Kellner,
                            Jacob Kozol, Jakub Rusz, Lars Karlitski, Martin
                            Sehnoutka, Ondřej Budai, Tom Gundersen