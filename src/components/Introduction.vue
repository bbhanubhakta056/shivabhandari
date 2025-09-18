<script setup>
import { ref } from 'vue'
  const pastExperience = ref([
      {
          position: "Student Volunteer Coordinator",
          organization: "University Community Service Club",
          period: "Aug 2020 - Dec 2021",
          description: "Managed a team of 50+ student volunteers, organized monthly community service events, and developed partnerships with local nonprofits.",
          icon: "fas fa-users"
      },
      {
          position: "Social Work Intern",
          organization: "City Youth Shelter",
          period: "Jun 2019 - Jul 2020",
          description: "Provided support to homeless youth, assisted in developing life skills workshops, and helped with resource coordination and advocacy efforts.",
          icon: "fas fa-hands-helping"
      },
      {
          position: "Campus Outreach Leader",
          organization: "Environmental Awareness Group",
          period: "Jan 2019 - May 2019",
          description: "Led campus sustainability initiatives, organized educational workshops, and mobilized students for environmental advocacy campaigns.",
          icon: "fas fa-leaf"
      }
  ]);

  const galleryImages = ref(Array(6).fill(null));

</script>

<template>
  <div id="app" class="max-w-6xl mx-auto px-4 py-8">
        <!-- Header/Navigation -->
        <header class="flex justify-between items-center py-6 mb-8 border-b">
            <div class="text-2xl font-bold text-blue-700">Your Name</div>
            <nav class="hidden md:flex space-x-8">
                <a href="#about" class="text-gray-600 hover:text-blue-700">About</a>
                <a href="#experience" class="text-gray-600 hover:text-blue-700">Experience</a>
                <a href="#gallery" class="text-gray-600 hover:text-blue-700">Gallery</a>
                <a href="#contact" class="text-gray-600 hover:text-blue-700">Contact</a>
            </nav>
            <button class="md:hidden text-gray-600">
                <i class="fas fa-bars text-xl"></i>
            </button>
        </header>

        <!-- Hero Section -->
        <section class="flex flex-col md:flex-row items-center mb-16">
            <div class="md:w-1/2 mb-8 md:mb-0">
                <h1 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">Student Leader & <span class="text-blue-700">Social Worker</span></h1>
                <p class="text-lg text-gray-600 mb-6">Dedicated to creating positive change through community engagement and leadership.</p>
                <div class="flex space-x-4">
                    <a href="#contact" class="bg-blue-700 text-white px-6 py-3 rounded-lg hover:bg-blue-800 transition">Get in Touch</a>
                    <a href="#gallery" class="border border-blue-700 text-blue-700 px-6 py-3 rounded-lg hover:bg-blue-50 transition">View Work</a>
                </div>
            </div>
            <div class="md:w-1/2 flex justify-center">
                <div class="w-64 h-64 bg-blue-200 rounded-full overflow-hidden border-4 border-white shadow-xl">
                    <!-- Replace with your actual photo -->
                    <div class="w-full h-full bg-blue-300 flex items-center justify-center">
                        <i class="fas fa-user text-6xl text-blue-600"></i>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="mb-16">
            <h2 class="text-3xl font-bold text-gray-800 mb-6">About Me</h2>
            <div class="bg-white p-8 rounded-xl shadow-md">
                <p class="text-gray-600 mb-4">I am a passionate student leader and social worker dedicated to making a positive impact in my community. With a strong belief in the power of collective action, I have initiated and participated in various projects aimed at addressing social issues and empowering marginalized groups.</p>
                <p class="text-gray-600 mb-4">My approach combines strategic leadership with grassroots activism, ensuring that initiatives are both impactful and sustainable. I believe in creating spaces where every voice is heard and valued.</p>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mt-8">
                    <div class="bg-blue-50 p-4 rounded-lg text-center">
                        <div class="text-blue-700 text-2xl font-bold">15+</div>
                        <div class="text-gray-600">Projects</div>
                    </div>
                    <div class="bg-blue-50 p-4 rounded-lg text-center">
                        <div class="text-blue-700 text-2xl font-bold">5+</div>
                        <div class="text-gray-600">Years Experience</div>
                    </div>
                    <div class="bg-blue-50 p-4 rounded-lg text-center">
                        <div class="text-blue-700 text-2xl font-bold">200+</div>
                        <div class="text-gray-600">Volunteers</div>
                    </div>
                    <div class="bg-blue-50 p-4 rounded-lg text-center">
                        <div class="text-blue-700 text-2xl font-bold">10+</div>
                        <div class="text-gray-600">Communities</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Experience Section -->
        <section id="experience" class="mb-16">
            <h2 class="text-3xl font-bold text-gray-800 mb-6">Experience</h2>
            
            <!-- Current Work -->
            <div class="mb-10">
                <h3 class="text-xl font-semibold text-gray-700 mb-4">Currently Working At</h3>
                <div class="bg-white p-6 rounded-xl shadow-md flex items-start">
                    <div class="bg-blue-100 w-16 h-16 rounded-lg flex items-center justify-center mr-6">
                        <i class="fas fa-building text-blue-700 text-2xl"></i>
                    </div>
                    <div>
                        <h4 class="text-lg font-bold text-gray-800">Community Outreach Coordinator</h4>
                        <p class="text-blue-700 font-medium">Youth for Change Initiative</p>
                        <p class="text-gray-600 mb-2">Jan 2022 - Present</p>
                        <p class="text-gray-600">Leading community engagement programs, organizing volunteer activities, and developing partnerships with local organizations to address youth-related issues.</p>
                    </div>
                </div>
            </div>
            
            <!-- Past Experience -->
            <div>
                <h3 class="text-xl font-semibold text-gray-700 mb-4">Past Experience</h3>
                <div class="space-y-6">
                    <div v-for="(job, index) in pastExperience" :key="index" class="bg-white p-6 rounded-xl shadow-md flex items-start">
                        <div class="bg-blue-100 w-16 h-16 rounded-lg flex items-center justify-center mr-6">
                            <i :class="job.icon" class="text-blue-700 text-2xl"></i>
                        </div>
                        <div>
                            <h4 class="text-lg font-bold text-gray-800">{{ job.position }}</h4>
                            <p class="text-blue-700 font-medium">{{ job.organization }}</p>
                            <p class="text-gray-600 mb-2">{{ job.period }}</p>
                            <p class="text-gray-600">{{ job.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Gallery Section -->
        <section id="gallery" class="mb-16">
            <h2 class="text-3xl font-bold text-gray-800 mb-6">Photo Gallery</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div v-for="(image, index) in galleryImages" :key="index" class="overflow-hidden rounded-xl shadow-md h-64">
                    <div class="w-full h-full bg-gray-200 flex items-center justify-center">
                        <i class="fas fa-image text-4xl text-gray-400"></i>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="mb-16">
            <h2 class="text-3xl font-bold text-gray-800 mb-6">Get In Touch</h2>
            <div class="bg-white p-8 rounded-xl shadow-md">
                <p class="text-gray-600 mb-6">Feel free to reach out for collaborations, volunteering opportunities, or just to say hello!</p>
                <form class="space-y-4">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-gray-700 mb-2" for="name">Name</label>
                            <input type="text" id="name" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                        </div>
                        <div>
                            <label class="block text-gray-700 mb-2" for="email">Email</label>
                            <input type="email" id="email" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                        </div>
                    </div>
                    <div>
                        <label class="block text-gray-700 mb-2" for="subject">Subject</label>
                        <input type="text" id="subject" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                    </div>
                    <div>
                        <label class="block text-gray-700 mb-2" for="message">Message</label>
                        <textarea id="message" rows="4" class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"></textarea>
                    </div>
                    <button type="submit" class="bg-blue-700 text-white px-6 py-3 rounded-lg hover:bg-blue-800 transition">Send Message</button>
                </form>
                <div class="mt-8 pt-6 border-t border-gray-100">
                    <h3 class="text-lg font-semibold text-gray-800 mb-4">Connect with me</h3>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-600 hover:text-blue-700"><i class="fab fa-linkedin text-2xl"></i></a>
                        <a href="#" class="text-gray-600 hover:text-blue-700"><i class="fab fa-twitter text-2xl"></i></a>
                        <a href="#" class="text-gray-600 hover:text-blue-700"><i class="fab fa-instagram text-2xl"></i></a>
                        <a href="#" class="text-gray-600 hover:text-blue-700"><i class="fab fa-facebook text-2xl"></i></a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="text-center py-8 text-gray-600 border-t">
            <p>© 2023 Your Name. All rights reserved.</p>
        </footer>
    </div>
</template>
