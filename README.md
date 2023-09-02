# Emrah's Blog

<br/>
<img src="Blog Gif.gif" alt="gif">
<br/>

<h2><b>About This Project:</b></h2>
<p>This blog web app was developed for my personal use, but since I haven't had the opportunity to create blog posts yet, the app is currently populated with fictitious posts. These fabricated posts consist of randomly generated titles, content, and images. They serve as a means for users to fully engage with all the features of the application. Feel free to explore the webpage as a demo user.</p>
<p>Prior to constructing this app, I reviewed a large array of blogs to find the features and designs that make a blog stand out. I wanted to ensure the front end was a balance between simplicity and attractiveness. Additionally, it needed to be distinct from a social media application. Many developers often succumb to the temptation of adding countless features, needlessly complicating what should be a straightforward app. To avoid this pitfall, I approached this project with a well-defined design and specific objectives in mind. These practices enabled me to develop a polished web application.</p>
<h3>Full Stack:</h3>
<p>
Every single tool presented below found it's utility at various stages during the development process. 
While not all of these tools constitute current components of the working code, each one was indispensable in the construction of this project. 
In the subsequent sections, a description of the utilization of each tool will be provided. 
The roster of tools includes the following:
</p>
<ul>
    <li>Python</li>
    <li>Flask</li>
    <li>PostgreSQL</li>
    <li>SQLite</li>
    <li>JavaScript</li>
    <li>HTML</li>
    <li>CSS</li>
    <li>Boostrap</li>
</ul>
<h3>Front End:</h3>
<p>
The tools employed for the development of the front end encompassed a combination of <b>HTML, CSS, Bootstrap, and JavaScript.</b>
HTML was augmented through the utilization of a jinja layout template, serving as the foundation for constructing each page. 
In the interest of honing my skillset, the extent of <b>CSS</b> usage was kept to a minimum, with a primary focus on harnessing the power of <b>Bootstrap.</b> 
The latter proved to be an invaluable asset, facilitating the expeditious creation of page layouts while ensuring optimal responsiveness. 
The majority of pages were skillfully crafted through the manipulation of containers, rows, and columns offered by the Bootstrap package. 
For the blog post display page, the BS 'album' class was elegantly employed to achieve a distinctive design flair.
</p>
<p>
In terms of frontend functionality, <b>JavaScript</b> served as the sole driving force. 
Its principal implementations manifested in the blog post display page, post editing, and account updates. 
The post display page, by default, presents all the available blog posts, however, these can be sorted either by specific categories or search queries.
Initially, only nine posts are visible, but through the simple act of clicking a 'load more' button, an API 'GET' request is dispatched to the server, dynamically fetching an additional nine posts. 
If no further posts are available, a user-friendly alert duly notifies the user of this circumstance.
</p>
<p>
For authenticated users, the capacity to edit their profile information is granted. 
This necessitates a preliminary <b>JavaScript</b> function to procure a CSRF security key from the server, a crucial requirement for authorizing any non-'GET' request. 
Armed with the security key, a 'PUT' request conveys all updated information to the server. Upon successful validation, the database promptly updates, and a <b>Flask</b> message conveys the outcome to the user.
</p>
<p>
There are privileges only accessible to an admin account, which includes the capability to upload, edit, and delete posts. 
The former task is accomplished through the utilization of an <b>HTML</b> form and back end form retrieval. 
As for the latter two responsibilities, <b>JavaScript</b> is entrusted with handling the underlying API interactions. 
Once again, the acquisition of the CSRF key precedes the 'PUT' request. 
In the context of post deletion, an appropriately tailored 'DELETE' request supersedes the 'PUT' counterpart.
</p>
<h3>Back End:</h3>
<p>
The tools harnessed in the backend development encompasses the following array: <b>Python, Flask, PostgreSQL, and SQLite.</b> 
I opted for <b>Python</b> as the backend programming language due to my expertise and proficiency in it, along with its vast collection of installable modules that offer remarkable flexibility.
From it's large library of modules, I incorporated the <i>WTForms, SQLAlchemy, SMTPlib, and Werkzeug</i> modules. 
When the contact form is submitted, the SMTPlib module is used to send an email to my personal inbox, providing the message details and sender's information.
Moreover, Werkzeug is utilized to hash and salt passwords in the database, ensuring utmost security.
</p>
<p>
<b>Flask</b>, distinguished by its lightweight nature, streamlined setup process, and accelerated development capabilities, was deliberately chosen over Django. 
The seamless integration of <i>WTForms and SQLAlchemy</i> modules tailored for <b>Flask</b> reinforced these benefits. 
WTForms did not substantially feature in this project because <b>HTML</b> forms were preferred for their simplicity. 
The predominant application of <i>WTForms</i> centered around its CSRF functionality, enabling the effortless addition of CSRF codes to each form.
</p>
<p>
Initially, the database was implemented through <b>SQLite</b>, but its limitations in handling certain functions necessitated a transition to <i>SQLAlchemy.</i> 
Nonetheless, in the project's initial iteration, <i>SQLite</i>, in tandem with the Python Faker module, facilitated the population of the database.
Eventually, when the decision was made to host the webpage online, <b>PostgreSQL</b> was utilized to host the database. 
</p>
<h3>Installation and Deployment:</h3>
<p>If you would like to take this project and copy it for personal use, you can following the following guide:
    <ol>
        <li>Fork the project</li>
        <li>Open the requirements.txt file and pip install all of the modules listed there</li>
        <li>Create a .env file
            <ul>
                <li>Inside this file, add a variable named "SECRET_KEY" with you Flask secret key</li>
                <li>Also, add your PostGres database url under the name "DATABASE_URL"</li>
                <li>Lastly, add "FLASK_APP=main"</li>
            </ul>
        </li>
        <li>Type into the command line "flask run"</li>
        <li>The app should now be running on local host</li>
        <li>All that's left to do is edit the frontend CSS to your personal liking</li>
    </ol>
The project contains all of the proper files for it to be deployed on Heroku. It only requires creating a heroku app and deploying the forked repository.
</p>
