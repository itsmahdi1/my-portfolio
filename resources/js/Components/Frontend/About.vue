<template>
    <section
        id="about"
        class="section bg-light-secondary dark:bg-dark-secondary"
    >
        <div
            class="container mx-auto"
            v-motion="{
                initial: {
                    y: 100,
                    opacity: 0,
                },
                visible: {
                    y: 0,
                    opacity: 1,
                },
            }"
        >
            <div class="flex flex-col xl:flex-row gap-24">
                <img
                    class="object-cover h-full w-[566px] md:mx-auto lg:mx-0 rounded-2xl"
                    src="/img/about.jpeg"
                    alt="about"
                />
                <div
                    class="flex flex-col items-center text-center lg:items-start lg:text-left"
                >
                    <div class="flex flex-col">
                        <h2
                            class="text-3xl lg:text-4xl font-medium lg:font-extrabold mb-3"
                        >
                            About Me
                        </h2>
                        <P class="mb-4 text-accent">Full Stack Web Developer</P>
                        <hr class="mb-8 opacity-90 dark:opacity-5" />
                        <p class="mb-8">
                            As a versatile web developer, I’m passionate about
                            creating seamless digital experiences that blend
                            functionality with aesthetic appeal. With a broad
                            skill set that spans front-end and back-end
                            development, I design and build dynamic websites and
                            applications that meet the needs of a global
                            audience.
                            <br />
                            <br />
                            Whether you're looking for a responsive web design,
                            a custom-built application, or a complete digital
                            solution, I bring creativity, technical expertise,
                            and a commitment to excellence to every project. My
                            goal is to help you achieve your vision by
                            delivering modern, scalable, and user-centric
                            solutions.
                        </p>
                    </div>
                    <a
                        href="#contact"
                        class="btn btn-md bg-accent text-light-tail-100"
                    >
                        Contact me
                    </a>
                </div>
            </div>
        </div>
    </section>
</template>
