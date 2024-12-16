<script setup lang="ts">
import { ref, computed } from 'vue';

const name = ref('');
const userEmail = ref('');
const password = ref('');
const passwordConfirmation = ref('');
const showPasswordRegister = ref(false);
const showPasswordRegisterConfirmation = ref(false);
const passwordMismatch = ref(false);
const emailError = ref('');
const nameError = ref('');
const passwordError = ref('');

const togglePasswordVisibilityRegister = () => {
    showPasswordRegister.value = !showPasswordRegister.value;
};

const togglePasswordVisibilityRegisterConfirmation = () => {
    showPasswordRegisterConfirmation.value = !showPasswordRegisterConfirmation.value;
};

const checkPasswordsMatch = computed(() => {
    return password.value === passwordConfirmation.value;
});

const validateEmail = (email: string): boolean => {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(String(email).toLowerCase());
};

const handleRegister = () => {
    emailError.value = '';
    passwordMismatch.value = false;
    nameError.value = '';
    passwordError.value = '';

    if (!name.value.trim()) {
        nameError.value = 'Please enter your name';
        return;
    }

    if (!validateEmail(userEmail.value)) {
        emailError.value = 'Please enter a valid email address';
        return;
    }

    if (!password.value.trim()) {
        passwordError.value = 'Please enter your password';
        return;
    }

    if (!checkPasswordsMatch.value) {
        passwordMismatch.value = true;
        return;
    }
    alert('Registration successful!');
};

const handleLogin = () => {
    emailError.value = '';

    if (!validateEmail(userEmail.value)) {
        emailError.value = 'Please enter a valid email address';
        return;
    }

    if (!password.value.trim()) {
        emailError.value = 'Please enter your password';
        return;
    }
    alert('Login sucessful!');
    userEmail.value = '';
    password.value = '';
};
</script>
<template>

    <body class="bg-[#09090B] text-white h-screen w-screen flex items-center justify-center">
        <div class="p-10">
            <Tabs default-value="login" class="w-96">
                <TabsList class="grid w-full grid-cols-2 ">
                    <TabsTrigger class="border border-slate-400 m-1 hover:scale-105" value="login">
                        Login
                    </TabsTrigger>
                    <TabsTrigger class="border border-slate-400 m-1 hover:scale-105" value="register">
                        Register
                    </TabsTrigger>
                </TabsList>
                <TabsContent value="login">
                    <Card>
                        <CardHeader>
                            <CardTitle>Login</CardTitle>
                            <CardDescription>
                                Make your login here. Click in 'get in' when you're done.
                            </CardDescription>
                        </CardHeader>
                        <CardContent class="space-y-2">
                            <div class="space-y-1">
                                <Label for="useremail">E-mail</Label>
                                <Input id="useremail" v-model="userEmail" />
                                <div v-if="emailError" class="text-red-500">
                                    {{ emailError }}
                                </div>
                            </div>
                            <div class="space-y-1 relative">
                                <Label for="password">Password</Label>
                                <Input id="password" v-model="password" :type="showPasswordRegister ? 'text' : 'password'" />
                                <button @click="togglePasswordVisibilityRegister" type="button"
                                    class="absolute right-2 top-1/2 transform -translate-y-1/2 pt-5">
                                    <span v-if="showPasswordRegister"><i class="ti ti-eye"></i></span>
                                    <span v-else><i class="ti ti-eye-off"></i></span>
                                </button>
                            </div>
                        </CardContent>
                        <CardFooter>
                            <Button @click="handleLogin" class="border border-slate-400 hover:bg-blue-900">Get
                                In</Button>
                        </CardFooter>
                    </Card>
                </TabsContent>
                <TabsContent value="register">
                    <Card>
                        <CardHeader>
                            <CardTitle>Register</CardTitle>
                            <CardDescription>
                                Register here. After saving, you'll be logged in.
                            </CardDescription>
                        </CardHeader>
                        <CardContent class="space-y-2">
                            <div class="space-y-1">
                                <Label for="name">Name</Label>
                                <Input id="name" v-model="name" />
                                <div v-if="nameError" class="text-red-500">
                                    {{ nameError }}
                                </div>
                            </div>
                            <div class="space-y-1">
                                <Label for="useremail">E-mail</Label>
                                <Input id="useremail" v-model="userEmail" />
                                <div v-if="emailError" class="text-red-500">
                                    {{ emailError }}
                                </div>
                            </div>
                            <div class="space-y-1 relative">
                                <Label for="register-password">Password</Label>
                                <Input id="register-password" v-model="password"
                                    :type="showPasswordRegister ? 'text' : 'password'" />
                                <div v-if="passwordError" class="text-red-500">
                                    {{ passwordError }}
                                </div>
                                <button @click="togglePasswordVisibilityRegister" type="button"
                                    class="absolute right-2 top-1/2 transform -translate-y-1/2 pt-5">
                                    <span v-if="showPasswordRegister"><i class="ti ti-eye"></i></span>
                                    <span v-else><i class="ti ti-eye-off"></i></span>
                                </button>
                            </div>
                            <div class="space-y-1 relative">
                                <Label for="register-password-confirm">Confirm your Password</Label>
                                <Input id="register-password-confirm" v-model="passwordConfirmation"
                                    :type="showPasswordRegisterConfirmation ? 'text' : 'password'" />
                                <button @click="togglePasswordVisibilityRegisterConfirmation" type="button"
                                    class="absolute right-2 top-1/2 transform -translate-y-1/2 pt-5">
                                    <span v-if="showPasswordRegisterConfirmation"><i class="ti ti-eye"></i></span>
                                    <span v-else><i class="ti ti-eye-off"></i></span>
                                </button>
                            </div>
                            <div v-if="passwordMismatch" class="text-red-500">
                                Password does not match.
                            </div>
                        </CardContent>
                        <CardFooter>
                            <Button @click="handleRegister" class="border border-slate-400 hover:bg-blue-900">Save new
                                register</Button>
                        </CardFooter>
                    </Card>
                </TabsContent>

            </Tabs>
        </div>
    </body>
</template>