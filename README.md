PHP Sitemap Generator
=====================

This class can be used to generate sitemaps and notify updates to search engines.

It can build a sitemap file from a list of URLs. The URLs may have attached the last modification date, a change frequency and a priority. The sitemap file may be saved in the compressed format.

The class may also update the site robots.txt file with the sitemap address.

When the sitemap is updated, the class can also notify search engines like Google, Bing, Yahoo and Ask.

Simple Example

        // include class
        include 'SitemapGenerator.php';

        // create object
        $sitemap = new SitemapGenerator("http://your.app.com/");

        // add urls
        $sitemap->addUrl("http://your.app.com",                date('c'),  'daily',    '1');
        $sitemap->addUrl("http://your.app.com/page1",          date('c'),  'daily',    '0.5');
        $sitemap->addUrl("http://your.app.com/page2",          date('c'),  'daily');
        $sitemap->addUrl("http://your.app.com/page3",          date('c'));
        $sitemap->addUrl("http://your.app.com/page4");
        $sitemap->addUrl("http://your.app.com/page/subpage1",  date('c'),  'daily',    '0.4');
        $sitemap->addUrl("http://your.app.com/page/subpage2",  date('c'),  'daily');
        $sitemap->addUrl("http://your.app.com/page/subpage3",  date('c'));
        $sitemap->addUrl("http://your.app.com/page/subpage4");

        // create sitemap
        $sitemap->createSitemap();

        // write sitemap as file
        $sitemap->writeSitemap();

        // update robots.txt file
        $sitemap->updateRobots();

        // submit sitemaps to search engines
        $sitemap->submitSitemap();
        ?>
