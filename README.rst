frontend-lib-special-exams-mitol
=================================

This is a react library responsible for extending learning app with special exams functionality, e.g. proctored/timed exams. 

Set up instructions
--------------------------

1. Clone your new repo:

  ``git clone https://github.com/mitodl/frontend-lib-special-exams-mitol.git``

2. Use node v12.x.

   Using other major versions of node *may* work, but is unsupported.  For convenience, this repository includes an .nvmrc file to help in setting the correct node version via `nvm <https://github.com/nvm-sh/nvm>`_.

3. Install npm dependencies:

  ``cd frontend-lib-special-exams-mitol && npm install``


Local Development
-----------------

For local development and testing follow these steps. (Learning MFE (``frontend-app-learning``) is the parent app of ``frontend-lib-special-exams-mitol``)

* Clone ``frontend-lib-special-exams-mitol`` into ``frontend-app-learning directory``.
* Change directory to the ``frontend-lib-special-exams-mitol`` and run the following commands:

    npm i

    npm build
* Verify a ``dist/`` folder has been created.
* Change directory back to ``frontend-app-learning`` and create a ``module.config.js`` file
* Place the following code in the module.config.js::

        module.exports = {
          localModules: [
            { moduleName: '@edx/frontend-lib-special-exams-mitol', dir: './packages/frontend-lib-special-exams-mitol', dist: 'src' },
          ],
        };
* Restart ``frontend-app-learning`` e.g. (``docker-compose restart frontend-app-learning``) and verify that it is using the local version from @mitol/frontend-lib-special-exams
* For css changes you might need to rebuild again.

Build Process Notes
-------------------

**Production Build**

The production build is created with ``npm run build``.

Internationalization
--------------------

Please see `edx/frontend-platform's i18n module <https://edx.github.io/frontend-platform/module-Internationalization.html>`_ for documentation on internationalization.  The documentation explains how to use it, and the `How To <https://github.com/edx/frontend-i18n/blob/master/docs/how_tos/i18n.rst>`_ has more detail.

